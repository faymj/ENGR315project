
### Purpose of program:

This program is designed to conduct some basic analysis on floating solar data from https://catalog.data.gov/dataset/high-resolution-floating-solar-pv-data
It has been designed to read data from datasets:
* FPV_Oakville_CA_Inverter1.csv
* FPV_Altamonte_FL_data.csv

The prior is primarily for considerations on solar power over time, and the latter is for comparisons on temperature and solar power output. The latter file is NOT provided on github due to it's size, and you will need to download it and place it in the same folder as this program for it to work (or adjust path as neccesary). To adjust files being read, see lines 9 and 10 for variables ``file_path``, ``file_path2`` respectively.

### Important considerations:

This program uses dataframes to solve questions 1 and 3, and iterating through variables for question 2. This method has some drawbacks in which program is known to suffer under the following conditions:
* A dataset of unexpected length or size is set as filepath (especially for Q2) typically results in a instant failure for any question,
* dataset features data from that was already previously mentioned (Q2 has some catches, but always creates at least one duplicate entry at the end).,
* dataset features more than 10,000,000 rows of data (second default path is approximately 1,000,000 rows and takes about 8 seconds to proccess, scale as neccesary for your dataset size).

This program makes the following assumptions about your dataset, please tweak these as neccesary:
* Q1 and Q2 assume your first dataset has the following datapoints per time in the order as presented: ``POINT, DAY, HOUR, ACPWRT, DCVOLT, RESIST, TEMPER, VL1TO2, VL2TO3, VL3TO1, ACCUR1, ACCUR2, ACCUR3, ACVLT1, ACVLT2, ACVLT3, ACFRQ1, ACFRQ2, ACFRQ3, APPWR1, APPWR2, APPWR3, ACPWR1, ACPWR2, ACPWR3, REPWR1, REPWR2, REPWR3``,
* All questions assume that all timings are 5 minutes apart,
* The number representing the day is a four digit YEAR, followed by a three digit DAY OF YEAR (e.g 2023220 is year 2023, day 220),
* You are on earth (probably not impactful, but you never know).

### Other notes:

Make sure you have the following systems integrated with python:
* ``pandas`` 
* ``numpy``
* ``matplotlib.pyplot``
* ``time``

All related files should stored in the same folder as each other (no hierarchy involved).
This project was done for ENGR315 in year of 2026, spring semester at JMU.
No current stances on permissions of use, so unless you are JMU faculty or support, contact us about it.
