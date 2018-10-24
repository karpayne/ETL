
Project Team: Karen Payne, Adam Zimmerman, and John McDonald

Using 2014 data from https://www.cdc.gov/nchs/data_access/VitalStatsOnline.htm#Births, we are extracting files and loading into a mySQL database. 

The following datasets will be extracted: 

1. Birth Data Files

Child, Mother, and Father data is extracted from the same fixed lenth data file.


Transformations will be done on the data in Jupyter, and then loaded into a structured data warehouse.

The data will be consolidated into a child, mother, and father dimention tables, each with a unique key to be used to join together.

Also required will be two lookup table in the data warehouse - Country and Dates - used to add additional attributes.  



The process of extracting the information from the source datafile produced a number of challenges. First, the large size of the .txt file combined with its nontraditional fixed width format resulted in large demands for system memory.  This issue was alleviated by splitting the .txt file into individual files each containing 1M recordings using a gitbash command. Processing the information in chunks of 1M required much less system memory, although resulted in four disctinct python scripts.  The source information was provided with a content 'user-guide' to help interpret the values and positions of the different variables along the fixed widths. The second issue encounted was that the user guide had a few typos that made it appear like the python script was failing to accurately read the file into dataframes.  This was solved by varifying that each column generated in the python dataframe matched with the .txt file in notepad++ and comparing against the expected values according to the user-guide. After parsing through the information, each variable from the source file could be pinpointed precisely in the generated dataframes. The final major problem encountered while extracting the data was the inconsistency of boolean variables.  Frequently, a boolean variable would be recorded as a blank space instead of 0 for False; The character widths of each column varied between rows, making variable extraction more difficult.  This was solved using the numpy .where function to create a boolean list of the rows of a target column to vary data extraction to satisfy the different character lengths.
