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
- VisComm["Average"]=VisComm[["Math","Electronics","GEAS","Communication"]].mean(axis=1)
- VisComm = VisComm.filter(items=['Name','Gender','Math','Electronics','Average'])

**Display the resulting DataFrame and its number of rows. Both filtering conditions must be applied to
the source dataset before the columns are selected.**

CODE:
- len(VisComm)

# B. VISAYAS FEMALE DATAFRAME

**Create a second DataFrame named VisFemale containing students whose Hometown is Visayas and
whose Gender is Female. Retain only: Name, Track, GEAS, Electronics, Average**

CODE:
- VisFemale = df.loc[(df["Hometown"] == "Visayas")&(df["Gender"] == "Female")]
- VisFemale["Average"]=VisFemale[["Math","Electronics","GEAS","Communication"]].mean(axis=1)
- VisFemale = VisFemale.filter(items=['Name','Track','GEAS','Electronics','Average'])

**Display VisFemale. Then display only the rows of VisFemale whose Average is at least 60. Do not
overwrite VisFemale when performing this second filter.**

CODE:
-  VisFemale.loc[(VisFemale['Average']>=60)]

# C. CATEGORY-AVERAGE VISUALIZATION 

**Examine how the recorded Average differs across the three categorical features Track, Gender, and
Hometown.**


**a. For each feature, compute the mean of Average for every category using Pandas.**

CODE:
- df["Average"]=df[["Math","Electronics","GEAS","Communication"]].mean(axis=1)

**b. Display the three summary tables.**

CODE:
- track_average=df.groupby("Track")["Average"].mean().reset_index()
- gender_average=df.groupby("Gender")["Average"].mean().reset_index()
- hometown_average=df.groupby("Hometown")["Average"].mean().reset_index()

**c. Create one figure containing three bar charts: mean Average by Track, by Gender, and by
Hometown.**

CODE:
fig,axes= plt.subplots(1,3,figsize=(12,5),sharey=True)

track_average.plot.bar(x="Track", y="Average", ax=axes[0], color="red")
axes[0].set_title("mean Average by Track")
axes[0].set_xlabel("Track")
axes[0].set_ylabel("mean Average")

gender_average.plot.bar(x="Gender", y="Average", ax=axes[1], color="Blue")
axes[1].set_title("mean Average by Gender")
axes[1].set_xlabel("Gender")
axes[1].set_ylabel("mean Average")

hometown_average.plot.bar(x="Hometown", y="Average", ax=axes[2], color="Green")
axes[2].set_title("mean Average by Hometown")
axes[2].set_xlabel("Hometown")
axes[2].set_ylabel("mean Average")


**d. Below the figure, write three concise statements identifying the category with the highest sample
mean for each feature.**

**Interpretation rule: Describe the observed dataset only. A difference in group means does not, by
itself, establish that a feature causes a higher board-exam score.**

## README File Version History
09/18/2026

**September 18, 2026** - Initial README output uploaded.
