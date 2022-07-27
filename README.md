# Pymaceuticals

# Opening the Project
Inside the Pymaceuticals folder there is a file called pymaceuticals.ipynb, please open this file with Jupyter Notebook. I will explain each part of my code as they appear in this ReadMe file. My code is annotated so please reference it as you see fit. 

# Cleaning the Data
First I checked my data for any mice ID's with duplicate timepoints. I use the .loc and .duplicated methods to find mice with duplicated IDs that also have duplicated timepoints. I want to remove these from our data because I can't determine which timepoint is correct. I remove the duplicated mouse from our data using the isin method. I double check to make sure my method removed our duplicate mouse. I started our with 249 mouse IDs and now have 248 mouse IDs.

# Summary Statistics
I group my clean data by drug regimen and then apply methods to find the mean, median, varience, standard deviation and standard error of the mean for the tumor volume. I put these values into a dataframe. 
I also find the same values by using the aggregation method.

# Bar and Pie Charts
With my grouped by drug regimen data, I used the value_count function to count how many times each regimen occured within our data set. I then plotted the data using pandas and by using pyplot. This can show us which drug allowed our mice to live the longest. However, we would also need to check to see how many mice used each regimen to get a better understanding. 

To make my pie chart for the sex of each mouse I first had to filter my data so that each mouse only appears once. I did this because some mice appear more times than other mice and I didn't want my count to be skewed. After this I put my sex data into a pie chart, one using pandas and the other using pyplot. The ratio of male and female mice look to be about equal for our data set. 

# Quartiles, Outliers and Boxplots
To find my quartiles and outliers for Capomulin, Ramicane, Infubinol, and Ceftamin for the final tumor volume, I use the drop duplicates method and keep the last value. I am able to use this method because my timepoints are in ascending order. I create an empty list to put each mouses' final tumor volume in for each treatment and a list for each treatment name. I use a for loop to find my interquantile ranges, the upper and lower bounds, and determine if there are any outliers for each drug. I print out the results.

Next I create my box plots using pyplot. 

# Lines and Scatter Plots
First I find a particular mouse to use by filtering my data by the drug "Capomulin". I then use the .unique method to create a list of all possible mice that used this drug. I do this in case we want to look at the data for another mouse. After picking a mouse, I filter my data again by the desired mouse ID, in this case r944. I plot this mouse's data for tumor volume vs time in a line plot. 

I then want to create a scatter plot of average tumor volume vs mouse weight for Capomulin. I first need to add a new column to my data frame that shows us the average tumor volume for each mouse. To do this I create a new dataframe that is grouped by mouse ID and finds the average tumor volume. I then merge this dataframe into my data that is filtered by Capomulin. I then use the drop duplicate method and keep the final weight of each mouse. I plot this data into a scatter plot. 

# Correlation and Regression
To find the correlation and regressio, I first use the linregress method for the average tumor volume and the final weight of my mice that used Capomulin. I create an equation of my line and plot it along with the same scatter plot as above. To find the correlation coefficient I use the pearsonr method. 

# Findings
It seems like Capomulin performed the best out of all of the other drugs tested. In the bar plot that counted the number of timepoints per treatment, Capomulin had the most timepoints which seems like the mice treated with that drug lived longer. I would like to investigate how many mice were present for other treatments and the average final time point for each mouse for a certain treatment. Out of the four drugs we investigated, Capomulin also had the smallest range of values which tells me that it performed consistently. I think it would be beneficial to look at all mice that were treated with Capomulin to see if there are any trends. I also found that for Capomulin there was a strong positive correlation between mouse weight and average tumor volume. I think it would be beneficial to investigate the effectiveness of the other treatments further, so we can draw more comparisons between all of the treatments.  




