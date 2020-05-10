# Bootcamp: UCB-VIRT-DATA-PT-03-2020-U-B-TTH

### Bootcamp Challenge #9 - 5/10/2020
Bootcamp Challenge 9: Module surfs_up

### Jupyter Notebooks Created
- [climate_analysis](climate_analysis.ipynb)

### Dataset Used
- [hawaii.sqlite](https://courses.bootcampspot.com/courses/140/files/36846/download?wrap=1)

### Challenge Description
The goals of this challenge are for you to:
- Determine key statistical data about the month of June.
- Determine key statistical data about the month of December.
- Compare your findings between the month of June and December.
- Make 2 or 3 recommendations for further analysis.
- Share your findings in the Jupyter Notebook.

## Methodology: 
Utilized SQLAlchemy ORM to upload the hawaii.sqlite DB into code objects. With an initial start_date of 2016-08-23, using code to get a date of exactly 365 days prior to the initial date of 2017-08-23, providing one calendar year worth of data points to analyze. 

### All describe() Statistics
- *Precipitation	Temperature*
- count	18103.000000	19550.000000
- mean	0.160644	73.097954
- std	0.468746	4.523527
- min	0.000000	53.000000
- 25%	0.000000	70.000000
- 50%	0.010000	73.000000
- 75%	0.110000	76.000000
- max	11.530000	87.000000

### June describe() Statistics
- *Precipitation	Temperature*
- count	1574.000000	1700.000000
- mean	0.136360	74.944118
- std	0.335731	3.257417
- min	0.000000	64.000000
- 25%	0.000000	73.000000
- 50%	0.020000	75.000000
- 75%	0.120000	77.000000
- max	4.430000	85.000000

### December describe() Statistics
- *Precipitation Temperature*
- count	1405.000000	1517.000000
- mean	0.216819	71.041529
- std	0.541399	3.745920
- min	0.000000	56.000000
- 25%	0.000000	69.000000
- 50%	0.030000	71.000000
- 75%	0.150000	74.000000
- max	6.420000	83.000000

### Analysis/Recommendations

### Key Differences June, December Observed:
1. The temperature ranges between June, December are (64-85)F, (56-83)F respectively. The difference in their ranges were (21, 27)F respectively. 
- **June**
- IQR(Q3 - Q1): (77 - 73) = 4
- 1.5 IQR: 1.5 * 4 = 6
- An outlier in June would be any temperature below 67F or any temperature above 83F.
- **December**
- IQR(Q3 - Q1): (74 - 69) = 5
- 1.5 IQR: 1.5 * 5 = 7.5
- An outlier in December would be any temperature below 61.5F or any temperature above 81.5F.

2. The precipitation ranges between June, December are (4.43-0)in, (6.42-0)in respectively. The difference in their ranges were (4.43, 6.42)in respectively. 
 **June**
- IQR(Q3 - Q1): (0.12 - 0) = 0.12
- 1.5 IQR: 1.5 * 0.12 = 0.18
- An outlier in June would be any precipitation above 0.40in.
- **December**
- IQR(Q3 - Q1): (0.15 - 0) = 0.15
- 1.5 IQR: 1.5* 0.15 = .225
- An outlier in December would be any precipitation above 0.375in.

3. Looking at the differences in temperatures between June and December, we can see that temperatures in June have a higher max and a higher min than those of December. The IQR for June is 4 and it is 5 for Dec, showing a greater variation in temperatures in Dec than in June. Any temperature below 67F or above 83F in June would be considered a statistical outlier; any temperature below 61.5F or above 81.5F in Dec would also be considered outliers.

4. For June an outlier is any day with precipitation over .40in and .375in for Dec. For both months, the 25% (Q1) were both 0 - these data points indicate that both months had a lot of days with 0in precipitation, allowing for outliers to occur at a relatively modest number of inches for both months. Dec showed a higher range of precipitation with it's Q3 .03in higher than June's Q3 and it's max was 6.42in while June's was 4.43in.

### Further Analysis
1. One area that this dataset is lacking is that it only provide one calendar year of data. It would not be possible be make high degree of accuracy as to whether or not these data points collected in June and December were reflect of normal conditions as displayed by trends over time, or if they were reflecting an anomaly for the year analyzed. In order to properly analyze this year of data in its correct context, we would request high level statistics (mean, standard deviation, median, 25%, 75% etc) as returned by the describe method on a year by year basis. Providing visual representation of the yearly dataset would provide high level contextual information.
2. A second limitation is that we are only taking into consideration two months of data, June and December - months that are more or less opposite of one another: Summer and Winter. It would be useful to analyze the other Summer months to properly benchmark June's data against July and August, likewise December against January and February. Knowing the statistics of the other Summer months and Winter months would allow us to know if June's and December's performances were indicative of normal trends in their respective season or if they were displaying unexpected behavior.
3. Thirdly, it would be useful to analyze the seasons of Fall and Spring, again with segmenting the data into individual months - so that we could not only benchmark June and December against their season's metrics, but furthermore how their season statistics compare to the other seasons and overall yearly averages. By only looking at June and December we are only gaining a sliver of the underlying dataset. 
4. This analysis did not require the calculation of median nor mode - it would be enlightening to know more about the distribution of precipitation across the months, it would be useful to know the number of days the precipitation > 0 throughout that month. If the month did not have many rainy days, the mode of that month would be expected to be 0.
