# Bryan Johnson's GWU Module 18 - Tableau&trade; Assignment READ ME File

## The files for this assignment can be found at the following repo:
https://github.com/bryanpijohnson/citi-bike-data

## The link to my Tableau Public&trade; file can be found here:
https://public.tableau.com/app/profile/bryan.test.johnson/viz/GWBCCiti-Bike-Data/Sheet1

## Within the repo link, you will find the following folders and files that contributed to the assignment:;

- **README.md** - that is this file :)
- **Resources** - this folder holds all of the CSV files that were utilized in the Tableau&trade; visualizations (with the possibility of other files there that were unused - it will be specified below).

## Initial Set Up and Issues

During the initial set up, I went to the site [Citi Bikes](https://s3.amazonaws.com/tripdata/index.html) to download the trip data. The instructions was specific that I should **not** download every ZIP file as it would be too much data for Tableau to handle. I opted to download all data from the years 2021, 2022, 2023 as that was 3 ZIP files. However, upon closer inspection, I found that each year had more data than Tableau&trade; could handle (over 15M rows), at least for the free version.

Due to this limitation, I initially opted to use just the 2023 data, from September forward, as this was the first month that had fewer than 15M rows throughout the rest of the year. However, trying to create visualizations with this much data dramatically slowed down the application and my ability to use the tool quickly. 

Once I knew this to be true, I added those corresponding files as a UNION within Tableau&trade;.

## Data Clean Up

Before I imported the CSV files, I made sure that the files had the same number of columns, with the same column names and data types in each column. I noticed that each CSV had the following 13 columns:

- ride_id (*varchar*)
- rideable_type (*varchar*)
- started_at (*timestamp*)
- ended_at (*timestamp*)
- start_station_name (*varchar*)
- start_station_id (*float*)
- end_station_name (*varchar*)
- end_station_id (*float*)
- start_lat (*float*)
- start_lng (*float*)
- end_lat (*float*)
- end_lng (*float*)
- member_casual (*varchar*)

I noticed immediately that both `end_lng` and `start_lng` were classified as numerical values and not geographical values. I immediately changed them to correspond to Longitudes.