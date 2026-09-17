# EXPERIMENT 4: DATA WRANGLING AND DATA VISUALIZATION
 Juliana Angelica L. Castro

2ECE-C

## Intended Learning Outcomes
At the end of this laboratory activity, the student should be able to:
1. filter tabular data using several categorical and numerical conditions;
2. construct focused DataFrames by selecting relevant features;
3. summarize the relationship between categorical features and a numerical variable; and
4. communicate a data comparison using clear and correctly labeled plots.

# A. VISAYAS COMMUNICATION DATAFRAME


**Create a DataFrame named VisComm containing students whose Hometown is Visayas and whose Track
is Communication. Retain only these columns, in the stated order: Name, Gender, Math, Electronics, Average**

CODE:
- VisComm = df.loc[(df["Hometown"] == "Visayas")&(df["Track"] == "Communication")]

**Display the resulting DataFrame and its number of rows. Both filtering conditions must be applied to
the source dataset before the columns are selected.**

CODE:
- 

# B. VISAYAS FEMALE DATAFRAME

**Create a second DataFrame named VisFemale containing students whose Hometown is Visayas and
whose Gender is Female. Retain only: Name, Track, GEAS, Electronics, Average**

CODE:
- VisFemale = df.loc[(df["Hometown"] == "Visayas")&(df["Gender"] == "Female")]

**Display VisFemale. Then display only the rows of VisFemale whose Average is at least 60. Do not
overwrite VisFemale when performing this second filter.**

CODE:
- 

# C. CATEGORY-AVERAGE VISUALIZATION 

**Examine how the recorded Average differs across the three categorical features Track, Gender, and
Hometown.**


**a. For each feature, compute the mean of Average for every category using Pandas.**

CODE:
- 

**b. Display the three summary tables.**

CODE:
- 

**c. Create one figure containing three bar charts: mean Average by Track, by Gender, and by
Hometown.**

CODE:
- 

**d. Below the figure, write three concise statements identifying the category with the highest sample
mean for each feature.**

CODE:
- 

**Interpretation rule: Describe the observed dataset only. A difference in group means does not, by
itself, establish that a feature causes a higher board-exam score.**
