
Project Team: Karen Payne, Adam Zimmerman, and John McDonald

Using 2014 data from https://www.cdc.gov/nchs/data_access/VitalStatsOnline.htm#Births, we are extracting files and loading into a mySQL database. 

The following datasets will be extracted: 

1. Birth Data Files
2. Period Linked Birth-Infant Death Data Files
3. Mortality Multiple Cause Files
4. Fetal Death Data Files

Transformations will be done on the data in Jupyter, and then loaded into a structured data warehouse.

The data will be consolidated into a child, mother, and father dimention tables, each with a unique key to be used to join together.

Also required will be two lookup table in the data warehouse - Country and Dates - used to add additional attributes.  




