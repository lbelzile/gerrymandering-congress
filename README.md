# A Study of Gerrymandering

This project began when we wanted to know more about the state of gerrymandering in the United States. Our interest and subsequent exploration seems timely given the amount coverage gerrymandering has received in the news recently. This is clearly an important issue that many people are concerned about, and that many more people should be made aware of. After researching the information out there, we decided to take a quantitative approach and collected, visualized, and analyzed relevant publicly available datasets to test our hypotheses about how political parties are able to gain a seemingly unfair advantage in Congress given the voter demographics of some states. Is gerrymandering an issue when it comes to our congressional districts? Do you feel that your congressperson represents your views? We hope you take the time to explore these questions and decide for yourself. Please contact us with questions and comments!

# Data sources and files

## Compactness

### Shapefiles and compactness calculations

- source: https://www.census.gov/geo/maps-data/data/tiger-line.html
- notebook: `python/get_compactness_score.ipynb`
- data: `data/compactness113_byGEO.json`

## Popular vote

### 2012

- source: manually downloaded and edited "Candidate Details" HTML table from http://www.thegreenpapers.com/G12/HouseVoteByParty.phtml
- data (raw): `data/113_2012_house_popular_vote.csv`
- notebook: `python/save_113_2012_house_popular_vote.ipynb`
- data (processed): `data/113_2012_house_popular_vote.json`

### 2014

#### Primary data (includes 3rd party votes)
- source: downloaded Sheet1 from https://docs.google.com/spreadsheet/ccc?key=0AjYj9mXElO_QdHVsbnNNdXRoaUE5QThHclNWaTgzb2c&usp=drive_web#gid=0 as CSV
  - This was found in the external links section of http://en.wikipedia.org/wiki/United_States_House_of_Representatives_elections,_2014
- data (raw): `data/114_2014_house_popular_vote.csv`
- notebook: `python/save_114_2014_house_popular_vote.ipynb`
- data (processed): `data/114_2014_house_popular_vote.json`

#### Secondary data (includes 2010 census data, not analyzed)
- Used in `python/nExpectedReps_compactSummary.ipynb`
- source: downloaded first sheet from https://docs.google.com/spreadsheets/d/1lGZQi9AxPHjE0RllvhNEBHFvrJGlnmC43AXnR8dwHMc/
- data: `data/114_2014_house_election_2010census.csv`

## Redistricting

- source: http://redistricting.lls.edu/who-partyfed.php
- notebook: `python/get_redistricting_authorities.ipynb`
- data: `data/redistricting_2010.json`

## PVI

### Districts

- source: http://cookpolitical.com/file/2013-04-49.pdf
- data: `data/pvi_district.csv`

### States

- source: http://cookpolitical.com/file/filename.pdf
- data: `data/pvi_state.csv`

## DIME

- source: http://data.stanford.edu/dime
- notebook: `python/DIME_load_save.ipynb`
- notes:
  - This data is not included in our repository, the data must be acquired from the link above.
  - We found issues in the dataset, particularly regarding the winner of some congressional elections. These were fixed to the best of our ability for our analyses.
  - Once the dataset is downloaded and fixed, running this notebook will produce the necessary data for the DIME analysis.
  - this notebook relies on a pickle file (`.pkl`) saved by `python/nExpectedReps_compactSummary.ipynb`

# Utilities

## Convert between state names, abbreviations, and FIPS numbers.

- `data/st2Fips.json`: State (2 letter abbreviation) to FIPS numbers
- `data/state2Fips.json`: State (full name) to FIPS numbers
- `data/st2State.json`: State (2 letter abbreviation) to full name
- `data/state2St.json`: State (full name) to 2 letter abbreviation

## Functions

`python/congress_tools.py`: collection of functions used in processing data

# Analysis

## Expected number of representatives

notebook: python/nExpectedReps_compactSummary.ipynb

## Compactness and Redistricting

notebook: python/Redistricting_and_compactness.ipynb

## Compactness and District PVI

notebook: python/Cooks_data_and_compactness_analysis.ipynb

## Gerrymandering Score

notebook: python/gerry_score.ipynb

## GM Score and DIME

notebook: python/DIME_analysis.ipynb

# Visualization

## Exporting for d3.js

notebook: python/export_data_for_visualization.ipynb

## Circles with district shapes

notebook: python/Maps_and_viz.ipynb
