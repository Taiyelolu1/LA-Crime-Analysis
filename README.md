# LA Crime Analysis
This project gives a detailed analysis of the LAPD crime data between 2020-2025. It shows an overview, victim demographic, crime breakdown, crime snapshot and resolution. The data used for this project was sourced from (look for the link to the dataset). 
### Project Background
The Los Angeles Police Department (LAPD) is the primary law enforcement agency of Los Angeles, California, United States. It is responsible for maintaining public safety, enforcing laws and preventing crimes. The department's organization includes 21 community stations (divisions).

The analysis of the LAPD crime data helps us understand the crime trends in Los Anegeles, the victim demographic and the resolution rate. It helps us with insights on the crime hotspots, target victims and peak crime periods. This helps us to make decisons as to how to reduce crime in Los Angeles.
### Overview of the Data
The data originally contained a table with multiple fields and records. The data was cleaned and transformed using the Power Query Editor in Power BI. The major transformations carried out in the Power Query Editor inlcude:
* Removal of duplicates in the unique DR_NO column (Division of Records Number).
* Removal of unwanted columns: The initial data had about 28 columns. 16 columns were removed due to inadequate information, and to allow for a more streamlined comprehensive analysis.
* Renaming Columns: Some columns were also renamed and capitalized for easy understanding in the course of the project.
* Replacing values: Columns with blank rows were replcaed with "Unknown". Records from the Victim Descent column were replaced based on the column description.
* Formatting columns: Records in the columns were trimmed, and given proper casing to give a better uniform look of the table. 
