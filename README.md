# Test_Name_Change
temporary repository to test name change

# Tableau_Challenge
Unit 20 Tableau Homework - Citi Bike Analytics - Student:  David Born

# Notes on Methodology

## Sampling
Because there were over 20 million records in the source trip data repository, a random 10% sample was taken to make the data size more manageable – particularly for Tableau. When the sample counts are displayed in a chart, you will see (0s) on the axis. For example:  Trips (0s). This indicates that the true count is 10x that shown on the chart.  Note, the sampling does not affect reported percentages, so where percentages are displayed, they represent the actual % and there is no need to apply a multiple factor. 

For relevancy, the time frame for the analysis is 2016 and later. To again limit the size of the data set, for year-over-year (YOY) calculations involving demographics the sample frame is confined to the busy 3rd quarter (3Q) summer months (July thru September). 

The source aggregated sales data was only available through May of 2019 (the last complete month).  This is reflected in the YOY sales trends that are reported in the Trend Overview dashboard.

## Data Staging
Source aggregated sales data was opened as quarterly csv files into MicroSoft Excel and merged manually. These files also contained data for trip distance. This data is aggregated by day.

Source trip data was read as monthly csv files into Python Pandas where the data was cleaned and merged. There were separate source files for New York City stations and Jersey City stations. This disaggregated data is at the trip level – one record per bike per trip. After cleaning and merging, new attributes were derived, such as calculating a rider’s age estimate from the “birth year” and “starttime” columns. 

Four Jupyter Notebooks used for the Pandas work are accessible via a link to GitHub [GitHub repository](https://www.citibikenyc.com/system-data) (NOTE: the downloaded source data is not cloned to GitHub due to its size. Rather, files with sample source records are included in the 'Resources' folder on GitHub.) Two notebooks each were used to compile and process data for two different time periods as follows.

## Time Period: Compile complete 12-month ride data for 2019
Notebooks:  

* combine_NY_JC_bike_files - this script combines separate 2019 monthly source files for New York and Jersey City and randomly samples the resulting data to create a reduced data set for Tableau.

* citi_bike - this script combines the 2019 monthly data into a single dataframe and processes the combined file further by cleaning data and creating additional variables.

## Time Period: Compile 2016 thru 2019 Citi Bike ride data for Year-Over-Year (YOY) analysis
Notebooks:

* YearOverYear_combine_NY_JC_files - Because the source data size is so enormous, the analysis is confined to the busiest ride season comprised of the months: July, August, and September. These months will enable study of peak rider participation for both members and those purchasing one-day or three-day passes. This script combines separate 2016-2019 monthly source files for New York and Jersey City and randomly samples the resulting data to create a reduced data set for Tableau.

* yoy_citi_bike - this script combines the 2016-2019 monthly data into a single dataframe and processes the combined file further by cleaning data and creating additional variables.


# Assignment Specifics

## Background

![Citi-Bikes](Images/citi-bike-station-bikes.jpg)

Congratulations on your new job! As the new lead analyst for the [New York Citi Bike](https://en.wikipedia.org/wiki/Citi_Bike) Program, you are now responsible for overseeing the largest bike sharing program in the United States. In your new role, you will be expected to generate regular reports for city officials looking to publicize and improve the city program.

Since 2013, the Citi Bike Program has implemented a robust infrastructure for collecting data on the program's utilization. Through the team's efforts, each month bike data is collected, organized, and made public on the [Citi Bike Data](https://www.citibikenyc.com/system-data) webpage.

However, while the data has been regularly updated, the team has yet to implement a dashboard or sophisticated reporting process. City officials have a number of questions on the program, so your first task on the job is to build a set of data reports to provide the answers.

## Task

**Your task in this assignment is to aggregate the data found in the Citi Bike Trip History Logs and find two unexpected phenomena.** 

**Design 2-5 visualizations for each discovered phenomena (4-10 total). You may work with a timespan of your choosing. Optionally, you may merge multiple datasets from different periods.** 

**The following are some questions you may wish to tackle. Do not limit yourself to these questions; they are suggestions for a starting point. Be creative!**

* How many trips have been recorded total during the chosen period?

* By what percentage has total ridership grown?

* How has the proportion of short-term customers and annual subscribers changed?

* What are the peak hours in which bikes are used during summer months?

* What are the peak hours in which bikes are used during winter months?

* Today, what are the top 10 stations in the city for starting a journey? (Based on data, why do you hypothesize these are the top locations?)

* Today, what are the top 10 stations in the city for ending a journey? (Based on data, why?)

* Today, what are the bottom 10 stations in the city for starting a journey? (Based on data, why?)

* Today, what are the bottom 10 stations in the city for ending a journey (Based on data, why?)

* Today, what is the gender breakdown of active participants (Male v. Female)?

* How effective has gender outreach been in increasing female ridership over the timespan?

* How does the average trip duration change by age?

* What is the average distance in miles that a bike is ridden?

* Which bikes (by ID) are most likely due for repair or inspection in the timespan?

* How variable is the utilization by bike ID?

**Next, as a chronic over-achiever:**

* Use your visualizations (does not have to be all of them) to design a dashboard for each phenomena.
* The dashboards should be accompanied with an analysis explaining why the phenomena may be occuring. 

**City officials would also like to see one of the following visualizations:**

* **Basic:** A static map that plots all bike stations with a visual indication of the most popular locations to start and end a journey with zip code data overlaid on top.

* **Advanced:** A dynamic map that shows how each station's popularity changes over time (by month and year). Again, with zip code data overlaid on the map.

* The map you choose should also be accompanied by a write-up unveiling any trends that were noticed during your analysis.

**Finally, create your final presentation**

* Create a Tableau story that brings together the visualizations, requested maps, and dashboards.
* This is what will be presented to the officials, so be sure to make it professional, logical, and visually appealing. 

## Considerations

Remember, the people reading your analysis will **NOT** be data analysts. Your audience will be city officials, public administrators, and heads of New York City departments. Your data and analysis needs to be presented in a way that is focused, concise, easy-to-understand, and visually compelling. Your visualizations should be colorful enough to be included in press releases, and your analysis should be thoughtful enough for dictating programmatic changes. 

## Submission 

Your final submission should include:

* A link to your Tableau Public workbook that includes: 
  * 4-10 Total "Phenomenon" Visualizations 
  * 2 Dashboards
  * 1 City Official Map
  * 1 Story 
* A text or markdown file with your analysis on the phenomenons you uncovered from the data.