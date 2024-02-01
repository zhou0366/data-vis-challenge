# data-vis-challenge

For this challenged, I heavily referenced class examples and the following online sites:
  https://docs.scipy.org/
  https://pandas.pydata.org/
  https://docs.python.org/
  https://realpython.com/
  https://scikit-learn.org/
  https://saturncloud.io/blog/how-to-check-for-duplicate-values-in-pandas-dataframe-column/
  
# Code Summary
## Analysis
  This challenge follows the instructions laid out in the jupyter notebook for examining results of drug testing on mice. We start by importing the data on each mouse and the data on tumor growth. The two resulting dataframes are merged on the Mouse ID for later data manipulation. Next, we search for a mouse which has duplicated data using the pandas dataframe duplicated function. We see that mouse g989 has multiple entries at certain timepoints so mouse g989 is dropped from the data frame.

## Summary Statistics

  Using the groupby function for each data summarization parameter, we create a summary dataframe containing mean, median, variance, standard deviation, and standard error. We also use the pandas aggregate method to create another dataframe as instructed for creating a single line line of summary statistics in the column names.

## Bar and Pie charts
  
  In this section, bar and pie charts using both pandas and pyplot. The bar chart breaks down the number of mice for each drug regimen and the pie chart displays the percentage of mice of male or female genders. From the bar chart, we see that there is a generally even amount of mice for each drug studied and a near 50/50 split of gender in the mice studied.

## Quartiles, outliers, and boxplots
  
  The mouse data dataframe is changed to only show the final tumor size by only grabbing rows with the max timepoint for each mouse ID. For each drug regimen, we create a dataframe for only mice in that drug regimen. Following examples used in classes, we calculate the quartiles, upper and lower q, iqr, upper and lower bounds for each drug regimen. Dataframes for the tumor data for mice in each drug regimen are also generated. Then, a box plot is created displaying the spread of final tumor sizes in each drug regimen. From these boxplots we see that Infubinol and Ceftamin show higher final tumor sizes. Capomulin and Ramicane both have similar medians but the standard deviation for both seem to mostly overlap. Perhaps additional comparisons between the two need to be performed.

## Line and scatter plots
  
  As the sample results show mouse l509, we will also use that mouse for the line plot, we will create a data frame containing only that mouse's data pulled from the main mouse study data frame. Then we will set the x axis to the timepoint and y axis to the tumor volume. This mouse's tumor size increases until 20 days after which it decreases.
  
  For the scatter plot, we set the x axis to the weight of mice in the Capomulin data frame and the y axis to the tumor volume. The scatter plot is then generated. We import the scipy stats library and then use linregress to calculate the linear regression and find an r squared of 0.77 indicating a fairly strong correlation between weight and tumor size.
