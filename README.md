### Introduction
####As data professionals, we must be familiar with how to work with date time objects and date strings. Therefore, using Python to cod, convert, manipulate, and group data is essential. Working with date strings often requires breaking them down into smaller pieces. Breaking date strings into days, months, and years allows you to group and order the other data in different ways so that you can analyze it. Manipulating date and time strings is a foundational skill in EDA.

####I will use a file called eda_manipulate_date_strings_with_python.csv, which comes from the bigquery-public-data.noaa_lightning.lightning_strikes public data table. It contains cloud-to-ground lightning strike information collected by Vaisala's National Lightning Detection Network (NLDN) and aggregated into 0.1° tiles by the National Centers for Environmental Information. This means that all the daily strikes within 0.1° latitude x 0.1° longitude are summed and assigned to a set of geographic coordinates that represents the center of the 0.1° “square” area. area.

### Objectives
####In this project, I will work with 2016–2018 lightning strike data from the National Oceanic and Atmospheric Association (NOAA) to calculate weekly sums of lightning strikes and quarterly lightning strike totals and plot them on bar graphs. Furthermore, I will convert date strings in the NOAA lightning strike dataset into datetime objects and combine these data objects into different groups by segments of time such as quarters and weeks.

### Steps
-Import packages and libraries, and read the data
-Create four new columns: week, month, quarter, and year. We can do this by using the datetime.strftime() method of the datetime object. o specify the information to extract, use the strftime format codes. In this case, I used %Y for year, %V for week number, %q for quarter.
-Plot the number of weekly lightning strikes. Let's start by filtering the original dataset to 2018. Use the groupby() and sum() functions to get the number of strikes per week.
-Next, use the plt.bar() function to plot the bar graph. Within the argument field, let's input the x-axis (the week column), then input the y-axis (or height) as the number_of_strikes column.
-Create a number_of_strikes_formatted column in the resulting dataframe by dividing by one million but also rounding to one digit after the decimal point, converting it to a string, and adding "M" to the end to represent millions.
-Create a grouped bar chart to better compare year-over-year changes each quarter. We can do this by creating two new columns that break out the quarter and year from the quarter column. We will use the quarter column and take the last two characters to get quarter_number, and take the first four characters to get year.

### Insights
-Weeks 32, 33 and 34 have the most number of lightning strikes.
-Quarter 3 of each year has the highest number of lightning strikes. Q3 of 2018 saw the highest followed by Q3 of 2016 and then 2017
