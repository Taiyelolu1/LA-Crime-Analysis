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

  The TimeOfDay ranges are:

  * 5AM-11AM = Morning
  * 12PM-5PM = Afternoon
  * 6PM-8PM = Evening
  * 9PM-4AM = Night
  
* **Report Delay (Days)**: This is the difference between the time the crime occurred and when it was reported.
* **Report Delay Band**: This groups the time difference between the time the crime occurred and when it was reported to give a clearer picture of the time gap.

Helper columns were created for the Age Band and Report Delay Band for proper sorting to help when visualizing the data. 

**Measures**
* **Total Crimes**: This counts the total records of crimes recorded between 2020-2025.
* **Victim Count**: This counts the total number of victims of the crimes. This is used in visualizing victims by descent and age band. 
* **Most Affected Area**: This shows the community with the highest crime records. 
* **Avg Victim Age**: This was created to get insights on the average age of crime victims.
* **Peak Crime Time**: This shows the time of the day with the highest crime activities recorded based on the grouping of the timestamps.
* **Top Crime Type**: This shows the top crime types based on the number of records. 
* **Previous Year Crimes**: This counts the total number of crimes for each of the previous years. This is to be used in calculating the YoY % Crime Change. 
* **YoY % Crime Change**: This visualizes the percentage change in crime rate from one year to another. 

Click here (Link to the file) to view the DAX functions used to create the measures, calculated columns, and table.

## Data Model
I created a relationship between the DateTable and the Date_Occ as well as the Date_Rptd. I also created a relationship between the Age Band helper table and the Age Band column as well as the Report Delay helper table and the Report Delay (Days) column. 

Insert snapshot of Data Model

## Data Analysis & Visualization
After completing the data cleaning and preparation, I began with my analysis and visualization. The visualizations were divided into four (4) report pages for easy navigation and clarity of analysis. These reports were used to effectively visualize key insights from this analysis.

Some Key Insights from the data visualization are summarized below:

1. **Overview**: This section gives an overwiew of the whole data.
   * There were a total of **1,005,198** crimes reported between 2020-2025 as of the time of analysis (the data is frequently updated).
   * The **Central community station** recorded the highest number of reported crimes, making it the most affected area during this period.
   * The average victim age was **29years**.
   * The peak crime time was at **Night**.
   * The average YoY % crime change between 2020-2025 was **8.09%**.
   * Notably, the year **2022** recorded the **highest number of reported crimes** with a total of **235,258** incidents.

Insert snapshot of the report.

2. **Victim Demographic**: This gives all the details about victims of the various crimes.
   * In terms of gender distribution, 40.18% of victims were males, 35.67% females and 24.14% listed as unknown. 
   * The age group with the highest number of victims was 20–39 years, accounting for 374,825 records. The least affected age group was 80 years and above, with 8,270 records.
   * Based on descent, the top victim groups were: Hispanic/Latin/Mexican, Unknown, White, Black and Other ethnicities.

Insert snapshot of the report 

3. **Crime Trends**: This section shows the trend of crimes with relation to time. 
   * The year-over-year (YoY) percentage change in reported crimes from 2020 to 2025 was: +5.02% (2021), +12.09% (2022), −1.24% (2023), −45.09% (2024), and −99.44% (2025), indicating significant fluctuations in crime trends over the years.
   * On average, the peak crime period occurred at night (9:00 PM – 4:00 AM), while the morning hours (5:00 AM – 11:00 AM) consistently recorded the lowest crime occurrence. However, the years 2020, 2024, and 2025 deviated from this trend, with afternoon hours (12:00 PM - 5:00 PM) emerging as the peak crime period.
   * Across the six-year period, the months with the highest reported crime counts were January, March, and October, indicating potential seasonal patterns in criminal activity.

Insert snapshot of the report 

4. **Crime Metrics**: This page is focused on ranking and concentration of crimes by location, type, and method.
   * The street consistently ranked as the top crime location (premise) from 2020 to 2025, marking it as a persistent crime hotspot throughout the period. Other frequently reported premises included: single family dwellings, multi-unit dwellings, parking lot, and other businesses.
   * The top five (5) LAPD stations/communities with the highest number of reported crimes were: Central, 77th street, Pacific, Southwest, and Hollywood.
   * The most common crime types reported were: vehicle stolen, battery – simple assault, burglary from vehicle, theft of identity, and vandalism.
   * Regarding weapon usage, the most frequently recorded were: Unknown (not specified/unrecorded), Strong-arm (bodily force), other weapons, verbal threat, and hand gun.

Insert snapshot of the report 

5. **Crime Resolution**: This page analyzes the reporting behaviour and the status progression of crimes reported.
   * The majority of crimes were reported within 48 hours of their occurrence, indicating relatively prompt victim or witness response in most cases.
   * In terms of case status, a large portion of the cases (803,946) remain under investigation as of the time of reporting. Only a smaller fraction has reached resolution, with the most notable outcomes being: Adult Other (109,255), Adult Arrest (86,877), Juvenile Arrest (3,249), Juvenile Other (1,864) and Unknown (7).

Insert snapshot of the report 

## Conclusion
This analysis of the Los Angeles crime dataset reveals clear trends in how, when, and where crimes occur across the city. Time-based analysis highlighted fluctuations in crime rates throughout the year, with noticeable peaks during specific months and time-of-day bands. Geographic breakdowns exposed high-risk areas and police divisions with consistently elevated incident volumes, emphasizing the need for targeted interventions.

Victim age bands and demographic insights showed that certain groups are more vulnerable to specific crime types, supporting the development of more tailored community safety programs. The delay between when crimes occur and when they are reported also varied widely, indicating potential barriers to timely reporting that could hinder case resolution.

Finally, analysis of case statuses and weapon usage offered operational insights that can help the LAPD and policymakers improve resource allocation, public awareness, and crime prevention strategies. This report serves as a foundation for ongoing monitoring, informed decision-making, and collaboration between law enforcement and the community.

## Recommendations
Based on the analysis and key insights derived from this project, I was able to come up with the following recommendations:
1. **Enhance Nighttime Patrols & Surveillance**
Since crimes peak at night (9:00 PM - 4:00 AM), targeted nighttime law enforcement visibility especially in high-risk areas like streets, parking lots, and densely populated neighborhoods can help deter criminal activity.

2. **Focus Resources on Central & High-Incidence Communities**
Given that Central, 77th Street, and Pacific communities are the most affected, LAPD should prioritize these divisions for preventive strategies, community engagement, and infrastructure improvements (e.g., lighting, cameras).

3. **Strengthen Vehicle Theft Prevention Campaigns**
With vehicle theft ranking as the top crime, launch public awareness campaigns and vehicle security programs in partnership with community groups and local media.

4. **Accelerate Case Resolution Processes**
With over 800,000 cases still under investigation, LAPD may need to review investigative workflows, optimize resource allocation, and possibly adopt digital tools to track and expedite case handling.

5. **Address Data Gaps** (e.g., 'Unknown' Weapon and Victim Info)
The high number of records with unknown victim sex, weapon type, or descent suggests data quality challenges. Recommend training for field officers on accurate data collection and system enhancements to reduce "unknown" entries.

6. **Tailor Victim Support Services by Demographics**
Since the majority of victims are aged 20–39, design support services and outreach programs targeting young adults—especially around identity theft, assault, and domestic incidents.

7. **Investigate Delay Patterns in Crime Reporting**
While most crimes are reported within 48 hours, delays in certain cases might reflect fear, lack of access, or mistrust. Conduct community research to uncover and address these barriers.

8. **Utilize Seasonal & Monthly Trends for Proactive Measures**
With spikes in crime seen in January, March, and October, LAPD can launch seasonal initiatives, public safety campaigns, and increased patrols around those months.


