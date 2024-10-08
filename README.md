# Electricity-Purchase-prediction README

# Overview

The Electricity Purchase Prediction tool is designed to assist customers who often find themselves unexpectedly out of electricity because they are unable to predict when they should make their next purchase. To address this issue, we developed a predictive model to help customers make more informed decisions about when to purchase electricity.
The dataset, extracted from various meter companies, includes the following information:
- SPN: Unique identifier of the user.
- SpnInstalledDate: Date when the meter was installed in the user’s home.
- Date: Date of the electricity purchase.
- Amount: The amount paid in GHC for the electricity purchased.
- ReferenceId: Receipt generated by the meter company, containing the company’s name and the receipt ID.

# Preprocessing
The data preprocessing involved the following steps:
- Data Cleaning: Removed records from companies with no ReferenceId.
- Meter Name Extraction: Extracted the meter company name from the ReferenceId.
- Data Grouping: Grouped the data by SPN and Date.
- Time Difference Calculation: Calculated the time difference between consecutive purchases.
- Statistical Analysis: Determined the mean, median, and skewness of the purchase intervals.
Based on the skewness of the data, the model uses either the median or mean to determine the next purchase date by adding the selected interval to the last recorded purchase date.

# PaymentPredictor Class
The PaymentPredictor class is designed to predict the next electricity purchase date for a customer using historical payment data stored in an SQLite database. 
The class provides methods to:
- Extract payment data.
- Calculate payment intervals.
- Predict the next payment date using a rolling window approach.
- Add new payment records to the database.
- Retrieve the predicted next payment date.
