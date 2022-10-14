# Analysis of Children's Hospital Patient Data

### Purpose of the Analysis

My Client-the hospital- wants to figure out how best to allocate resources and reduce costs. They have requested an analysis of past patient data to determine how the most common trends in demographic and diagnostic data affect hospital costs. The data was filtered, sorted, augmented with calculated columns, and statistically analysed for any findings that might be useful. This report contains both the analysis as well as Final Recommendations.

### Methodology
I followed the standard Data analytics methodology.I was able to skip step one as the original data file (Excel) – which had been downloaded from Kaggle – was provided to me. It was stored locally in Excel format while I did the wrangling and data analysis.

### Exploratory Data Analysis
In exploring the dataset, I discovered that there was data from 500 patients – with ages ranging from 0 (below a year) to 17.The data set also included Sex as a binary variable (female sex coded as 1), the length of  hospital stay in days,the race of the patient coded numerically(1 to 6), the diagnosis code for the patients illness and the total hospital charges for each patient.To perform meaningful analysis for the Client, I would need to add additional columns of encoded dummy variables for the race attributes

### Research Questions
- What age frequents the Hospital the most and what age has the maximum expenditure ?
- What diagnosis group has the most hospitalisation days and the highest expenditure?
- What are hospital costs by age and gender ?
- Can the length of stay be predicted from age, gender, and race since they are the most  crucial factor for inpatients ?
- What variable mainly affects the hospital costs?

### Data Wrangling
There was no need to do a lot of Data Wrangling of the data as it was provided in clean and complete excel spreadsheet format. However, I added some additional columns of *calculated* data in order to complete the analysis these columns were encoded dummy variables for the race attributes

### Data Analysis
For the Analysis the Excel Spreadsheet with the raw data was copied into a new spreadsheet called **Working sheet Hospital costs**.
I inserted a pivot table on another sheet called **Hospital costs pivot table**. I added the Age variable in the rows, and count of age, sum of total charges and average total charges for each age in the columns. I then used conditional formatting to highlight the areas of interest and, we can see that children under a year accounted for over half of all patients in the dataset and they had the highest sum of total charges. However, on average patients aged 9,3,5, and 6 had the highest expenditure

I inserted another pivot table on the same **Hospital costs pivot table**. I added the diagnosis codes in the rows, and count of length of stay, average length of stay,sum of total charges and average total charges for each diagnosis code in the columns. In order to visualise this better, I created a scatter plot of average charge versus length of stay.

It showed that most of the points were below 20,000 dollars charge and 5 days stay.I was looking for diagnosis codes with high expenditure and low length of stay - points in the upper left corner of the plot- while trying to avoid low expenditure and high length of stay diagnosis.

For analysing hospital costs by age and gender, on the **Hospital costs pivot table**, I put the sex and age variables in the rows, and sum of total charges and average total charges for each sex and age in the columns. I then used conditional formatting to highlight the areas of interest. On average male patients spent 500 dollars more than females. Females aged 3 and 9 had the highest average charge which is consistent with what was observed in the initial overall analysis while for males, ages 5 and 3 had the highest average charge.


In order to find out if length of stay can be predicted from age, gender, and race, I created a table with the age and gender variable. I then used the **IF function** to encode dummy variables for the Race variable so I could run a regression analysis on it using the Excel data analysis pack. I ran the analysis on a new sheet called **Hospital costs Regression Sheet**.

The P-values for the variables do not show significance. I appears you cannot predict length of stay from a conglomerate of all these values

Finally, I ran a regression analysis on all the variables to see if I could predict hospital costs. Length of stay, age and sex had significant p-values.



## Recap of Final Conclusions

- Children under a year old accounted for the most frequent patients, while children aged 9 and 3 had the highest average hospital costs both being over 10k dollars
- Patients with diagnosis code 911 had the highest expenditure paying about 48000 dollars on average for a staying an average of 7 days while those with code 609 had the longest average  hospital stay of 41 days with an average cost of 29000 dollars
- On average male patients spent 500 dollars more than females. Females aged 3 and 9 had the highest average charge which is consistent with what was observed in the initial overall analysis while for males, ages 5 and 3 had the highest average charge
- You cannot predict length of stay from a conglomerate of the age, gender, and race variables, however it may be a different story if the variables are examined individually and i would recommend further analysis here
- Length of stay, age and sex could be used to predict hospital costs, there p-values were less than 0.05 and their co-efficients suggest  that for each extra day stayed hospital costs increase by 740 dollars, for each year of age hospital costs increase by 115 dollars and finally, female patient costs are lower by about 1000 dollars
