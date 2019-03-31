# Data Cleaning Assessment

[![N|Solid](https://cldup.com/dTxpPi9lDf.thumb.png)](https://nodesource.com/products/nsolid)

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Cleaning Needs for the Open Powerlifting csv by column assessment:

  - Name: combine results for individuals, clean up duplicates 
  - Sex: needs nothing
  - Event: need pandas to subset for "SBD" (squat bench deadlift) only
  - Equipment: pandas subset to remove
  - Age: need to denote missing values, round float values down and make an int
  - Division: pandas subset to remove
  - Bodyweight: pandas subset to remove
  - WeightClass: pandas subset to remove
  - Squat1Kg, Squat2Kg, Squat3Kg, Squat4Kg: pandas subset to remove
  - Best3SquatKg: denote missing values and combine duplicate values for Names
  - Bench1Kg, Bench2Kg, Bench3Kg, Bench4Kg: pandas subset to remove
  - Best3BenchKg: denote missing values and combine duplicate values for Names
  - Deadlift1Kg, Deadlift2Kg, Deadlift3Kg, Deadlift4Kg: pandas subset to remove
  - Best3DeadliftKg: denote missing values and combine duplicate values for Names
  - TotalKg: pandas subset to remove
  - Place: pandas subset to remove
  - Wilks: pandas subset to remove
  - McCulloch: pandas subset to remove
  - Tested: pandas subset to remove
  - AgeClass: denote missing values
  - Country: pandas subset to remove
  - Glossbrenner: pandas subset to remove
  - IPFPoints: pandas subset to remove
  - Federation: pandas subset to sort on US Federations
  - Date: pandas subset to sort on 2016, 2017, & 2018 and denote missing values
  - MeetCountry: pandas subset to sort on USA
  - MeetState: pandas subset to sort on US states
  - MeetName: pandas subset to remove

# Cleaning Time

  - Pandas should take a couple hours for subsets.
  - For duplicates, calculations like rounding, and coding for missing values should take a day or two at most.
  - I anticipate hand coding/edits time devoted to cleaning taking 5 minutes at most.

# Attribution
The Open Powerlifting csv being used in this project was downloaded from the site openpowerlifting.org and is available for open source use in the public domain under the Data tab/heading on the site. Sample attribution text is provided: "This page uses data from the OpenPowerlifting project, https://www.openpowerlifting.org. You may download a copy of the data at https://gitlab.com/openpowerlifting/opl-data." The Open Powerlifting Database is maintained by librarians and archivists who powerlift and get the data from powerlifters self-submission and also crawling meets data published. 

# Semantic Contents

 - The file contains data held in the public domain.
 - The information being used from the dataset will include participant names, those who participated in all three SBD events, the best of the 3 lifts in each event SBD, US country and states meets, state location, date, and sex of the participant.
 - Data collection for this project occurred in March 2019. Open Powerlifting collects as new data is presented throughout the year(s).

# Collection Process

1. Data was retrieved from https://www.openpowerlifting.org/data
2. The openpowerliftingcsv was downloaded.
3. That file was uploaded into FileZigZag review to convert from csvbz2 to zip.
4. The files were extracted from the zip and saved as a Excel csv.
5. This version failed to import into Jupyter Notebook.
6. The original file and all copies were deleted from the computer
7. Step 1 was repeated on a different day after downloading 7zip.
8. The file was opened with 7zip and then imported into Jupyter Notebook unsuccessfully.
9. The files were removed from the computer.
10. From box.illinois.edu, the downloaded openpowerlifting csv was opened and saved.
11. Then, imported successfully into Jupyter Notebook.

# Data Structure
The data format is stored in a csv file.
The entities in this file are Participants and Meets. Participants are represented by Name and Meets are represented by Country, State, and Federation.
There are 1,343,621 rows/records and 37 columns/properties in the original csv.
Data types include float, integer, text/char, and date.

# Column/Property Description
Column Details:
 - The Name column contains first and last name of each lifter.
 - The Sex column contains the biological sex of each lifter.
 - The Event column contains an abbreviation for the lift event the lifter participate(s).
 - The Equipment column contains information about whether or not the lifter used equipment in  their lift event.
 - The Age column contains the age of the participant at the time of the meet.
 - The Division column contains the category and classification of the lifting event the lifters participated in for their event(s). 
 - The Bodyweight column contains the weight in kilograms of the lifter at the time of weigh in for the meet.
 - The WeightClass column contains the classification range that the lifter was placed in at the time of weigh in.
 - The Squat1,2,3,4 columns are the number of attempts/lifts a lifter did in the squat event in kilograms.
 - The Best3Squat is the highest number in kilograms from the Squat1,2,3,4 columns.
 - The Bench1,2,3,4 columns are the number of attempts/lifts a lifter did in the bench event in kilograms.
 - The Best3Bench is the highest number in kilograms from the Bench1,2,3,4 columns.
 - The Deadlift1,2,3,4 columns are the number of attempts/lifts a lifter did in the deadlift event in kilograms.
 - The Best3Deadlift is the highest number in kilograms from the Deadlift1,2,3,4 columns.
 - The TotalKg column contains the sum of the Best3Squat, Best3Bench, and Best3Deadlift in kilograms lifted for that participant.
 - The Place column contains the position in the competition that the lifter was awarded the day of the event.
 - The Wilks, McCulloch, and Glossbrenner columns contain formulas that calculate the overall strength of each lifter based on the lifts they did for the day in kilograms.
 - The Tested column contains whether the participant was tested or not.
 - The AgeClass column contains the age range classification the lifter was in at the time of the meet.
 - The Country column is to show the country of origin for the lifter.
 - IPFPoints column contains a federation point system.
 - The Federation column contains the name of the federation hosting the meet.
 - The Date column contains the month, day, and year the meet occurred.
 - The MeetCountry column contains the country the meet took place in.
 - The MeetState column contains the state the meet took place in.
 - The MeetName column contains the name of the meet that the lifter participated in.

Data Values and Units:
 - date (month, day, year)
 - float (decimals for age, weights in kg)
 - integer (age and ageclass)
 - text/char (name, sex, event, location)

Missing Values:
There are no codes for missing values. They appear as blank intersections of data or blank cells.  The reason for missing values is because they were not provided by lifter and/or not reported by the organization that publishes meet results.

Unique Values:
 - The WeightClass column contains a (+) symbol for the youth weight classes. 
 - The Squat1,2,3,4; Bench1,2,3,4; and the Deadlift1,2,3,4 columns contain (-) symbol denoting a decrease in weight lifted on those attempts.

Caveats:
A lot of the information and details described above will not be relevant with the final data file as many of the properties/columns are being removed in subsets of the original data file.
