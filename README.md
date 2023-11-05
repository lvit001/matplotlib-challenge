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
- 
