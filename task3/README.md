# Task 3: Supplier-Buyer Matching with BigQuery & SQL

For this task, I took the raw supplier and buyer data, cleaned it up, merged it, and then matched suppliers to buyers using SQL on BigQuery. The goal was to create a recommendation table that helps buyers find the right materials.

<b>Note: Please review this [Jupyter notebook](https://github.com/IpshitaSingh/Assignment-VS/blob/main/task3/Task3_Documentation_VanillaSteel.ipynb) for more extensive documentation including the code.</b>

---

## Tools Used
- **BigQuery** – Storing and querying data
- **SQL** – Merging and filtering datasets
- **Pandas** – Cleaning and preprocessing data
- **Excel/CSV** – Handling input and output

---

### Data Preparation

The Excel files had column names with special characters (like `/` and `()`), which needed to be renamed for easier processing. After this, I changed the file type to CSV to enable uploading to Big Query.

### Merging Supplier Data in BigQuery

There were only two common columns between the datasets: Quantity and Weight. As all the fields were relevant for buyer preferences, I added the non-matching columns as 'null' for each table accordingly.

### Matching Suppliers to Buyer Preferences

The recommendation table was built using SQL. Since the datasets had a lot of missing fields, I kept the join conditions flexible:
- Weight and Quantity being mandatory matching criteria.
- Grade, Finish, Thickness, and Width are optional, so suppliers can still match buyers even if they lack those details.

### Exporting the Recommendations

The final recommendations table could be exported as a CSV file from BigQuery. Since the dataset is relatively small (~300 rows), a manual copy-paste into Excel was done for easier review.

---

## Summary

- Cleaned messy column names 
- Merged supplier data while keeping all useful fields 
- Built a recommendation system prioritizing weight & quantity but allowing flexibility 
- Exported results for review 



