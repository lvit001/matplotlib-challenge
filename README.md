# matplotlib-challenge
## Module 5 Challenge Assignment
### Prepare the Data
- Began by merging the mouse_metadata and study_results files using pd.merge on Mouse ID through a left merge
- To find the number of mice, used a len function on the unique data in the Mouse ID column
- To figure out which Mouse ID was duplicated, did a loc function as well as a duplicated function that looked at both the Mouse ID and Timepoint columns to find the Mouse ID that repeated over the same time points. Used the unique function to grab just one of the list of duplicated values for g989. Information on how to use the duplicated function was found [here]([url](https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.duplicated.html)https://pandas.pydata.org/docs/reference/api/pandas.DataFrame.duplicated.html). 
### Prepare the Data
