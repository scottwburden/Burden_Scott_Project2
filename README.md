# Burden_Scott_Project2

Author: Scott Burden

Date: November 18, 2026

This is a class project using EPA data on air pollutants around the RDU
airport in Durham, NC from January 1, 2018 to April 30, 2020 
to investigate associations between those air pollutants and severity of sickle
cell symptoms. 

The project does not cover any investigation into correlations between air
pollutants and sickle cell. It mainly concerns cleaning datasets to produce
one measure per date, turning those cleaned measurements into tables with 
statistically meaningful information, and producing plots to visualize the
tables.

I used tidyverse Version 2.0.0 to clean my crude data and make ggplots. I used
version 1.9.4 of lubridate to reshape dates written in a way that is unfriendly
to R. I used gtsummary to make the table of average pollutant levels over the 
entire study period. 

The three CSV files are EPA files of the date-by-date data for carbon monoxide,
PM2.5, and ozone for the year listed in their title at the EPA's Raleigh-Durham
Airport monitoring site. 

data-7 is the ZIP file containing another folder called data, which holds the
three CSV files with the pollutant measurements for each day within the 
observation period. However, I copied the files outside the data folder because
I found it easier to work with them outside.

The R Markdown contains the code needed to run the program. One should also be
able to access the Markdown from the Project file. 

The Word render of the R Markdown should also be present in the folder.
              
              
              HOW TO REPRODUCE

1. Download R version 4.5.2, and connect RStudio to it.

2. Open RStudio and open a Markdown.

3. Download all of the requisite packages.

4. mr_clean is the name I gave to my function, which takes the three CSV files,
reads them in, loops through them, modifies the the syntax of the dates so that
they are usable in R, averages pollutant readings if there are multiple for the
same date for that year and deletes extra values for that date.
The final product in that function should be a cleaned data frame.

5. To call the function, specify which file you want read for the first 
argument. The second argument will default to "ppm" and produce the ozone
measurements in parts per million. To get ozone in parts per billion, specify
"ppb" for the second argument.

6. The tables section in the Markdown code file produces tables with the mean
value for each pollutant as well as the minimum and maximum levels of each 
pollutant for each year 2018 through 2020. Note that 2020 was cut off at the
end of April instead of New Year's Eve. 

7. I put the re-formatting to make the plot in the same code chunk as each plot
itself. Feel free to make them separate chunks if it helps you, but it helps
me to keep them together. My first plot is a scatterplot of CO and ozone per
month with the measurements for each year bucketed by month. The first plot 
needed error bars, so I had to make the confidence interval contents in my 
data-wrangling step before the plot. The second plot was a line plot color-
coded by year. To get both the dots and the lines, I needed both a geom_point()
and a geom_line() in my ggplot statement.

8. I knitted my final report into a Word document.
