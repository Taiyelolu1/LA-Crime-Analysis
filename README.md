# LA Crime Analysis
This project gives a detailed analysis of the LAPD crime data between 2020-2025. It shows an overview, victim demographic, crime breakdown, crime snapshot and resolution. The data used for this project was sourced from (look for the link to the dataset). 
## Project Background
The Los Angeles Police Department (LAPD) is the primary law enforcement agency of Los Angeles, California, United States. It is responsible for maintaining public safety, enforcing laws and preventing crimes. The department's organization includes 21 community stations (divisions).

The analysis of the LAPD crime data helps us understand the crime trends in Los Angeles, the victim demographic and the resolution rate. It helps us with insights on the crime hotspots, target victims and peak crime periods. This helps us to make decisons as to how to reduce crime in Los Angeles.
## Overview of the Data
The data originally contained a table with multiple fields and records. The data was cleaned and transformed using the Power Query Editor in Power BI. The major transformations carried out in the Power Query Editor inlcude:
* Removal of duplicates in the unique DR_NO column (Division of Records Number).
* Removal of unwanted columns: The initial data had about 28 columns. 16 columns were removed due to inadequate information, and to allow for a more streamlined comprehensive analysis.
* Renaming Columns: Some columns were also renamed and capitalized for easy understanding in the course of the project.
* Replacing values: Columns with blank rows were replcaed with "Unknown". Records from the Victim Descent column were replaced based on the column description.
* Formatting columns: Records in the columns were trimmed, and given proper casing to give a better uniform look of the table.
* Added column: Added a new column "Hour" by extracting the hour from the column Time_Occ.

**The CrimeData** having gone through numerous transformations in the Power Query Editor was left with the following columns:
* Dr_No: Division of Records Number.
* Date_Rptd: Date crime was repoerted.
* Date_Occ: Date crime occurred.
* Time_Occ: Time the crime occurred.
* Area Name: A designated name that references a landmark or surrounding community where the patrol division is responsisble for.
* Crime: Indicates the crime committed.
* Victim Age: Indicates the age of the victim.
* Victim Sex: Indicates the sex of the victim.
* Victim Decent: Indicates the victim's decent.
* Premise: The location where the crime took place.
* Weapon: The type of weapon used in the crime.
* Status: Status of the case.

***The CSV file generated from the Power Query Editor have been included in the repository for this project. The CSV file for the main table wasn't attached due to it's size, but it can be downloaded here*** (don't forget to add link)

## Tools used 
1. **Power BI**: This was the major tool used in this project. Power BI was used in creating the visualization and report for the insights generated from this project. Power BI service, a component of Power BI was also utilized in creating a web link that allows interactivity and navigation with the report.
2. **Power Query Editor**: This is an advanced feature of Power BI that allows transformation to be carried out on a dataset. The Power Query Editor was used in carrying out transformations across different columns such as removing duplicates, formatting columns, replacing values, etc.

## Project Workflow
A Project Workflow provides a good structure for every data analytics project. It helps to establish a clear roadmap of sequential steps from the initial problem to the final insights. This keeps the project organized and aligned with goals. It also outlines tasks within each project phase, preventing important elements from being overlooked and making the process more efficient. The workflow for this project includes:
1. Project objective.
2. Data collection.
3. Data cleaning and preparation.
4. Data analysis and visualization.
5. Interpretation and reporting.

## Project Objective
The objective of this project is to analyze crime data from the Los Angeles Police Department (LAPD) from 2020-2025 to uncover patterns, trends, and high-risk areas across time, location, and crime types. Using Power BI, the project aims to provide interactive dashboards that support data-driven insights for public safety awareness, resource allocation, and strategic decision-making.

## Data Collection 
The data for this project was collected from (name the place and leave a possible link). The data included records of various crimes, date reported, weapons used, places they occurred across different locations in LA and others as listed in the data overview above.
## Data Cleaning & Preparation
The data cleaning process began in the Power Query Editor in Power BI. Here, some major operations such as removal of duplicates, and removal of unwanted columns were done. Other text operations such as capitalising, trimming, and replacing values were also carried out on some columns. The M Query Codes (put the link) from the Power Query Editor have been attached to this repository. Please note that the Power Query Editor automatically writes/generates these codes based on the steps applied in the editor.

After data cleaning, a new column **Hour** was created by extracting the hours from the column **Time_Occ**. This was done in the Power Query Editor. 

Outside Power Query Editor, a **DateTable** was created using the minimum date from the column Date_Occ and maximum date from the column Date_Rptd. The table contained columns for date, year, Month Number, Month, Day number and Day. This table was marked as the date table. A new relationship was then created between the DateTable and the Date_Occ as well as the DateTable and Date_Rptd. 

In addition, I created new measures and new columns to provide in-depth insights into the various crime records. Some of these measures and columns include:

**Columns**
* **Age Band**: This column was created to group the different ages to simplify analysis and highlight at-risk groups.
* **TimeOfDay**: Instead of analyzing crime by exact timestamps (e.g., 21:47 or 03:15), these bands provide a clear summary of crime patterns across the day.
* **Report Delay (Days)**: This is the difference between the time the crime occurred and when it was reported.
* **Report Delay Band**: This groups the time difference between the time the crime occurred and when it was reported to give a clearer picture of the time gap.

Helper columns were created for the Age Band and Report Delay Band for proper sorting to help when visualizing the data. 

**Measures**
* **Total Crimes**: This counts the total records of crimes recorded between 2020-2025.
* **Most Affected Area**: This shows the community with the highest crime records. 
* **Avg Victim Age**: This was created to get insights on the average age of crime victims.
* **Peak Crime Time**: This shows the time of the day with the highest crime activities recorded based on the grouping of the timestamps.
* **Top Crime Type**: This shows the top crime types based on the number of records. 
* **Previous Year Crimes**: This counts the total number of crimes for each of the previous years. This is to be used in calculating the YoY % Crime Change. 
* **YoY % Crime Change**: This visualizes the percentage change in crime rate from one year to another. 

Click here (Link to the file) to view the DAX functions used to create the measures, calculated columns, and table.
