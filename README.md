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

## Step 3: I identified businesses that were awarded contracts every year (2018, 2019, 2022, and 2023) based on step 1 above

1. I merged contracting All_2018_Contracting.csv and All_2019_Contracting.csv into one file (All_2018TO2019_Contracting_manual.csv) containing ONLY the businesses that received federal contracts those two years in a row. RESULT: 29,587 businesses were NOT awarded contracts from 2018 to 2019; and 198,187 businesses were awarded contracts in 2018 and 2019.
2. I then merged the All_2018TO2019_Contracting files and All_2022_Contracting to determine which businesses were awarded contracts in 2018, 2019, and 2022 consecutively. RESULT: 64,875 businesses that had been awarded contracts from 2018 to 2019 WERE NOT awarded contracts in 2022 (2018_2019_BUT_NOT_2022.csv) and 139,012 businesses were awarded contracts in 2018, 2019, and 2022 consecutively (All_2018TO2022_Contracting_manual.csv).
3. I then merged All_2018TO2022_Contracting_manual.csv with All_2023_Contracting.csv to determine which businesses were awarded contracts in 2018, 2019, 2022, and 2023 consecutively. RESULT: 63,284 businesses that had been awarded contracts in 2018, 2019, and 2022 WERE NOT awarded contracts in 2023 (2018_2022_BUT_NOT_2023.csv); and 101,351 businesses were awarded contracts in 2018, 2019, 2022, and 2023 consecutively (All_2018TO2023_Contracting_manual.csv).
4. #### OVERALL RESULT: 101,351 businesses were awarded contracts in 2018, 2019, 2022, and 2023 consecutively (File names: All_2018TO2023_Contracting_manual.csv and All_2018_To_2023_Contracting).

## Step 4: I identified businesses that were NOT awarded contracts POST-COVID (2022 and 2023). 
1. I merged csv files of businesses that had been awarded contracts in 2018 and 2019 BUT NOT in 2022 and 2023 (2018_2019_BUT_NOT_2022.csv and 2018_2022_BUT_NOT_2023.csv), removed duplicates and saved the file as 2022_2023_NO_Contracting_manual.csv. Then, I cross-referenced with 2023 contracting recipients (which I removed) and saved the file as 2022_2023_NO_Contracting.csv.
2. In the process, I found that 34,177 businesses WERE NOT awarded contracts in 2018, 2019, and 2022, BUT RECEIVED CONTRACTS in 2023. I saved those in a separate csv file (NoContracts2018to2022_ONLY2023.csv).
6. ##### OVERALL RESULT (a): I found that 13,477 businesses WERE NOT awarded contracts in 2022 and 2023 (2022_2023_NO_Contracting.csv).
7. Next step: Determine whether the 13,477 businesses above are still active. 
