# DataCleanAndFormatted

## This is my second deliverable.
Both the cleaning and formatting were done in R Studio. 

Info about the data sets used can be found [here](https://github.com/DataPreProcessing-FALL2024/Deli1Test).

YOU CAN SEE THE CLEANING/FORMATTING CODE [HERE](https://datapreprocessing-fall2024.github.io/Deli2Test/)!

## Summary of Cleaning/Formatting Steps
### Laptop Data
#### Cleaning
1. Load packages and read in CSV file from Github link.
2. Clean column names and remove first column.
3. Removed all rows that are completely blank and checked every other column for NAs.
4. Change '?' to NA.
5. Remove wording around the screen resolution dimensions so values are more standardized.
6. Fix capitalization, duplicate values, and incorrect values in the 'cpu' column.
7. Remove the string 'GB' from all cells in 'ram_gb' column.
8. Change repetitive or duplicate values in 'gpu' column manually.
9. Remove the string 'KG' from all cells in 'weight_kg' column.
10. Save clean data to 'DataCleanAndFormatted' folder.
#### Formatting
1. Read in Clean_Laptop_Data CSV file from Github link.
2. Make all text lowercase in 'company', 'model', 'cpu', 'memory', 'gpu', and 'operating_system' columns.
3. Make sure all columns that should be numeric are read in that way already or manually convert them using as.numeric()- 'inches', 'ram_gb', 'weight', 'price'
4. Save formatted data to 'DataCleanAndFormatted' folder as RDS file.
### IMDB Data
#### Cleaning
1. Load packages and read in CSV file from Github link.
2. Clean column names and remove unnecessary columns like 'imdb_id' or that have a lot of missing values like 'x'.
3. Remove row 14 since it does not contain any values.
4. Clean 'duration_min' column by changing certain values and empty cells to NA, as well as cleaning an individual cell with a typo.
5. Clean 'country' column by making sure all values are spelled correctly.
6. Clean 'content_rating' column by replacing a certain string with NA as well as changing 'Not Rated' to 'Unrated'.
7. Clean 'income' column by removing a very small outlier and removing dollar signs and commas. Also have to replace instances of the string 'o' with '0'.
8. Clean 'votes' column by removing all instances of periods.
9. Clean 'release_day' column by changing all dates to be of one equivalent format.
10. Clean individual cells with misspellings in the 'imdb_score' column.
11. Save clean data to 'DataCleanAndFormatted' folder.
#### Formatting
1. Read in Clean_IMDB_Data CSV file from Github link.
2. Make all text lowercase in 'title', 'genre', 'country', 'content_rating', and 'director' columns.
3. Make sure all columns that should be numeric are read in that way already or manually convert them using as.numeric()- 'duration_min', 'income', 'votes', 'imdb_score'
4. Change 'release_day' column to be recognized as DateTime format.
5. Save formatted data to 'DataCleanAndFormatted' folder as RDS file.
### Real Estate Data
#### Cleaning
1. Load packages and read in CSV file from Github link.
2. Clean column names and remove unnecessary columns like 'url' and 'listing_title'.
3. Change all values of the 'property_type' column to either be 'Residential Apartment' or 'Commercial Space'.
4. Split up the 'property_size' column into 'size_sqft' and 'remove' to separate the numbers from the string 'Sq Ft'.
5. Remove the 'property_size' and 'remove' columns.
6. Remove commas and leading spaces from the new 'size_sqft' column, then move that column back to its original position in the dataframe.
7. Convert blank cells into NA values.
8. Remove unnecessary strings in the 'parking' column to only be left with a single number. Also remove leading spaces from the column and change 'N/A' to an NA value.
9. Remove unnecessary strings in the 'elevator' column to only be left with a single number. Change some values to NAs and replace all strings that start with 0.
10. Remove unnecessary strings in the 'floor' column. Change 'ground' for ground floor to 0. Make some values NAs that are not explained well ('Full Building', etc.). Make sure everything fits a similar format.
11. Remove unnecessary strings in the 'price_bdt' column. Remove commas and leading spaces. Convert cells with lakhs and crores (types of currency) into bdt. 
12. Split 'price_bdt' column into 'new_price_bdt' and 'remove' columns to remove unnecessary strings after a space separator. Remove 'price_bdt' and 'remove' columns. Move 'new_price_bdt' column back to original position.
13. Remove unnecessary strings in the 'service_charge_bdt' column. Remove commas and leading spaces. Turn some values into NAs or 0s and manually change certain values.
14. Split 'service_charge_bdt' column into 'new_service_charge_bdt' and 'remove' columns to remove unnecessary strings after a space separator. Remove 'service_charge_bdt' and 'remove' columns. Move 'new_service_charge_bdt' column back to original position.
15. Get rid of leading spaces in the 'building_registration_type' column. Replace individual strings that are near duplicates so it ends up having less categories- 'Residential', 'Commercial', 'Residential & Commercial', or NA.
16. Get rid of leading spaces in the 'preferred_tenants' column and replace individual strings that are near duplicates of others.
17. Get rid of leading spaces in the 'furnished' column. Manually change all values to either be 'Furnished', 'Semi-Furnished', 'Un-Furnished', or NA.
18. Remove different variations of the string 'Sq Ft' from the 'garage_size_sqft' column. Remove all instances of periods in this column.
19. Get rid of leading spaces in the 'front_road_size_ft' column and remove all variations of 'Ft'. Remove all instances of periods in this column.
20. Get rid of leading spaces in the 'common_area_size_sqft' column and remove all variations of 'Sq Ft'. Remove all instances of periods in the column. Change one unknown value and an extreme outlier to NAs.
21. Remove all instances of the string 'Bedrooms' occuring in the 'bedrooms' column as well as the string '+ 01 Study Room'. Remove all instances of 0s in the column to get rid of the 0s in front of the number of bedrooms.
22. Remove all instances of the string 'Bathrooms' occuring in the 'bathrooms' column. Remove all instances of 0s in the column to get rid of the 0s in front of the number of bathrooms.
23. Create a 'new_location' column that has 5 possible values- 'Chanpara Bazar', 'Banani', 'Gulshan', 'Baridhara Diplomatic Zone', and 'Tejgaon'. If certain keywords are in the original location column, they will be changed to one of these five values. Move the 'new_location' column behind the original 'location' column and remove the original.
24. Change new column names back to original names.
25. Save clean data to 'DataCleanAndFormatted' folder.
#### Formatting
1. Read in Clean_Real_Estate_Data CSV file from Github link.
2. Make all text lowercase in 'property_type', 'building_registration_type', 'preferred_tenant', 'furnished', 'location' and 'country' columns.
3. Make sure all columns that should be numeric are read in that way already or manually convert them using as.numeric()- 'size_sqft', 'year_built', 'parking', 'elevator', 'price_bdt', 'service_charge_bdt', 'garage_size_sqft', 'front_road_size_sqft', 'common_area_size_sqft', 'bedrooms', and 'bathrooms'.
4. Save formatted data to 'DataCleanAndFormatted' folder as RDS file.
