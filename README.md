# Oct2023_DataMerge_PPPUSAs
October 23, 2023 Updated Version of Data for Government Contracting 2018 to 2023 and PPP loans

## The purpose of this repository is to identify the following categories:

1. US small businesses that were awarded federal government contracts in 2018, 2019, 2022, and 2023 (pre- and post-covid).
2. US small businesses that received PPP loans in 2020 and 2021.
3. US small businesses that were awarded federal government contracts in 2018 and 2019 (pre-covid), received PPP loans in 2020 or 2021, and contracts in 2022 and 2023 (post-covid).
4. US small businesses that were awarded federal government contracts in 2018 and 2019 (pre-covid), DID NOT receive PPP loans, then received contracts in 2022 and 2023 (post-covid).
5. US small businesses that were awarded federal government contracts in 2018 and 2019 (pre-covid), received PPP loans in 2020 or 2021, BUT NO CONTRACTS in 2022 and 2023 (post-covid). 
6. US small businesses that were awarded federal government contracts in 2018 and 2019 (pre-covid), received NO PPP loans in 2020 or 2021 and NO CONTRACTS in 2022 and 2023 (post-covid).

### Question: are the businesses in categories 5 and 6 still active? Did they survive? 

The period (COVID) 2020 to 2021 is not included since it represents the period when the Paycheck Protection Program (PPP) was being implemented. 

## Step 1: I retrieved government contracting data from 2018 to 2019, then from 2022 to 2023

The data are large and were obtained from USASpending.gov's Award Data Archive (https://www.usaspending.gov/download_center/award_data_archive) and came in multiple (6 to 7) csv files for each year. 

Each file is large (2GB) and has around 1 million entries with multiple entries per business to document each contract. 

I wrote Python code to access the content of each file, filter by "small business" and "USA", then aggregate the data (summed dollar amounts etc...) to only have one row per business. 

## Step 2: For each year, I combined the different sub files into one main file with all the contracting data for that year.

For each year, I wrote Python code to combine all sub-files into one main csv file with all the contracting data resulting in the following files:
1. All_2018_Contracting.csv
2. All_2019_Contracting.csv
3. All_2022_Contracting.csv
4. All_2023_Contracting.csv

## Step 3: I identified businesses based on step 1 above

1. I merged contracting All_2018_Contracting.csv and All_2019_Contracting.csv into one file (All_2018TO2019_Contracting_manual.csv) containing ONLY the businesses that received federal contracts those two years in a row. 
