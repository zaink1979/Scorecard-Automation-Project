# Scorecard-Automation-Project

## Summary

We are working on raw datasets related to street, sidewalks, business Improvement districts which are needed to organize, arrange, structure, and format according to open data policy and technical standards manual. In the end, uploading datasets to Open Data Portal and making sure that data is user-friendly. In this project, we will covert raw data file (Monthly Street Cleanliness historical data) to be converted into a final file ready to be uploaded to Open Data Portal while using Open Refine (ETL) tool.

## Procedure

A step-by-step guided process to direct the reader through whole process is as follow:

Step 1: Fill down cells in columns in “Borough” and “District”

Step 2: Create column “geography” based on “column Borough” using expression 
grel:value.replace("Manhattan","Community Distrist")

Step 3: Create “column timeframe” based on column “Borough” using expression 
grel:value.replace("Manhattan","Month")

Step 4: Create column “service” based on column “Borough” using expression 
grel:value.replace("Manhattan","Street Cleanliness")

Step 5: Create “column cd_full_title” based on column “District” using expression 
grel:value.replace("MN","Manhattan Community District").replace("BX", "Bronx Community District").replace("BKN","Brooklyn Community District").replace("QE","Queens Community District").replace("SI","Staten Island Community District")

Step 6: Create column “cd_short_title” based on column “cd_full_title” using expression 
grel:value.replace("Manhattan Community District","Manhattan CD ").replace("Bronx Community District", "Bronx CD ").replace("Brooklyn Community District","Brooklyn CD ").replace("Queens Community District","Queens CD ").replace("Staten Island Community District","Staten Island CD ")

Step 7: Create column “borocd” based on column “cd_short_title” using expression 
grel:value.replace("Manhattan CD ","1").replace("Bronx CD ","2").replace("Brooklyn CD ","3").replace("Queens CD ","4").replace("Staten Island CD ","5")

Step 8: Text transform on cells in column borocd using expression value.toNumber()

Step 9: Rename different columns like “Borough” to “borough”, “District” to “district”, and “Cleaning Section” to “cleaning_section”. Basically, we want to have every column heading in “lowercase” and put “Underline” in between word spaces.


