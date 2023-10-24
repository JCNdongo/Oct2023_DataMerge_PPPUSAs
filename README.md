# Oct2023_DataMerge_PPPUSAs
October 23, 2023 Updated Version of Data for Government Contracting 2018 to 2023 and PPP loans

## The purpose of this repository is to identify the following:

1. Small businesses that were awarded government contracts in 2018 and 2019 (pre-covid)
2. Small businesses that were awarded government contracts in 2022 and 2023 (post-covid)
3. Small businesses that were awarded government contracts in 2018 and 2019 (pre-covid) then 2022 and 2023 (post-covid), and received PPP loans.
4. Small businesses that were awarded government contracts in 2018 and 2019 (pre-covid) then 2022 and 2023 (post-covid), but DID NOT receive PPP loans.
5. Small businesses that were awarded government contracts in 2018 and 2019 (pre-covid) BUT NOT in 2022 and 2023 (post-covid), and received PPP loans.
6. Small businesses that were awarded government contracts in 2018 and 2019 (pre-covid) BUT NOT in 2022 and 2023 (post-covid), and DID NOT receive PPP loans.

The period (COVID) 2020 to 2021 is not included since it represents the period when the Paycheck Protection Program (PPP) was being implemented. 

## Step 1: Retrieved government contracting data from 2018 to 2019, then from 2022 to 2023

The data are large and were obtained from USASpending.gov's Award Data Archive (https://www.usaspending.gov/download_center/award_data_archive) and came in multiple (6 to 7) csv files for each year. 

Each file is large (2GB) and has around 1 million entries with multiple entries per business to document each contract. 

I wrote Python code to access the content of each file, filter by "small business" and "USA", then aggregate the data (summed dollar amounts etc...) to only have one row per business. 
