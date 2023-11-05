# matplotlib-challenge
## Module 5 Challenge Assignment
### Prepare the Data
- Began by merging the mouse_metadata and study_results files using pd.merge on Mouse ID through a left merge
- To find the number of mice, used a len function on the unique data in the Mouse ID column
- To figure out which Mouse ID was duplicated, did a loc function as well as a duplicated function that looked at both the Mouse ID and Timepoint columns to find the Mouse ID that repeated over the same time points. Used the unique function to grab just one of the list of duplicated values for g989. Information on how to use the duplicated function was found [here](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.duplicated.html).
- Completed the option code to find all of the data for the duplicated mouse ID with a loc function that looked for that specific mouse ID in the Mouse ID column
- To remove the duplicate mouse ID, created a new data frame that removed the duplicate mouse ID rows via a loc function that included all but the duplicate mouse ID
- Rechecked the number of mice via a len function of unique mouse IDs
### Summary Statistics
- To calculate summary statistics by drug regimen, used a groupby function to group the data but drug regimen
- Using the new data frame grouped by drug regimen, using the mean, median, var, std, and sem functions on the data frame, specifically the tumor volume column
- Created a data frame with all of the summary stats data and displayed it.
- Discovered the aggregate function [here](https://www.geeksforgeeks.org/python-pandas-dataframe-aggregate/#) and used it to calculate the same summary statistics in one line of code! magical :)
### Bar and Pie Charts
- For the pandas bar chart, first created a data frame using the drug groupby from the previous section that counted the values in the timepoint column. Sorted this data from highest to lowest using sort_values. Then used the plot function with kind=bar to create a pandas bar chart with the data
- For the pyplot bar chart, set the x-axis equal to the index values (which were the drug regimens) and the y-axis equal to the time points column. Then, used plt.bar along with the x-axis and y-axis data to display the chart. Also used xticks and rotation to rotate the labels on the x-axis. Code for rotating labels found [here](https://www.pythoncharts.com/matplotlib/rotating-axis-labels/#:~:text=Option%201%3A%20plt.&text=xticks()-,plt.,way%20to%20rotate%20your%20labels.).
- For the pandas pie chart, created a new data frame that took the value counts of the sex column in cleaned_df. Renamed the count column to Sex so that would show on the y label. Used the plot function and kind=pie to create the pie chart.
- For the pyplot pie chart, set colors and then used plt.pie with the new mouse_sex data frame.
### Quartiles, Outliers and Boxplots
- Began by creating a new dataframe using loc that only contained the four requested drugs in the drug regimen column.
- Then, used a groupby function on the new data frame to group by the Mouse_ID column. Used the max function to get the max of all of the columns in the new data frame.
- Had the new data frame only contain the Timepoint column, which would have the max timepoint for each mouse ID because of the last line of code
- Merged the new greatest_tp data frame with the original cleaned_df to get all of the other data for the Mouse IDs at their final timepoint.
- Created a list with the four requested drug regimens
- Created an empty list for tumor volume data
- Added in code to calculate quartiles, IQR, and bounds for all of the data
- Created a for loop that looped through each of the treatments. The for loop would create a new data frame based on the drug regimen in the list it was on and pull data from the tumor volume column for each row with that drug regimen. Then added the tumor volume data to the previously empty tumor volume data list.
- Added a subset that would look for the quartiles, IQR, and bounds data for each of the drugs in the list and then print out their IQR and data for any potential outliers
- Used code from class to create a boxplot that used the data in the tumor volume data list. Added labels to the x-axis to be able to tell which data was for each drug.
### Line and Scatter Plots
- Line Plot: Randomly decided to use mouse ID b128 (it was the first one in my data frame) and created a data frame that only contained data for that mouse ID. Set the x-axis equal to time points for b128's data frame and the y-axis equal to tumor volume for b128's data. Used pyplot to create the line plot
- Scatter Plot: Created a new data frame that only looked at data for Capomulin. Grouped the data frame by mouse ID and then took the mean for both the tumor volume column and weight column by mouse ID. Set the x-axis as the mouse weight data and the y axis as the tumor volume data. Used pyplot to create a scatter plot with the data
### Correlation and Regression
- Used the scipy pearsonr function to get the correlation coefficient for the mouse weight vs tumor volume data.
- Used code from class to set slope, intercept, rvalue, pvalue, stderr values equal to the data retrieved from the scipy linregress function for the mouse weight vs tumor volume data.
- Set a variable of regress_values equal to the function of a line (x_axis value * slope + y-intercept)
- Set a variable of line_eq equal to printed code to be able to display the linear equation function
- Finally, replotted the data as well as the regression line and annotated the linear equation over the chart
