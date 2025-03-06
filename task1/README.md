# Task 1: Supplier Data Cleaning and Preprocessing

This task involved preprocessing of two supplier data files, including standardization of their formats, data cleaning, and merging relevant information into a single dataset.

Note: Documentation is also available on this Jupyter notebook

## Steps Taken

### 1. Backup
Created a copy of the original folder to prevent data loss.

### 2. Preprocessing supplier_data_1
- Standardized column names by removing special characters and spaces for compatibility with BigQuery.
- New column names:
  
  | New Column Name            | Original Column Name |
  |----------------------------|----------------------|
  | material_quality           | Werksgüte |
  | order_grade_description    | Bestellgütentext |
  | nominal_thickness_mm       | Nenndicke NNN.NN mm mit Dezimalpunkt |
  | width_mm                   | Breite |
  | length_mm                  | Länge |
  | weight_kg                  | Gewicht (kg) |
  | material_cluster           | Cluster |
  | si_content                 | Si-Gehalt |
  | mn_content                 | Mn-Gehalt |
  | p_content                  | P-Gehalt |
  | s_content                  | S-Gehalt |
  | cr_content                 | Cr-Gehalt |
  | ni_content                 | Ni-Gehalt |
  | mo_content                 | Mo-Gehalt |
  | v_content                  | V-Gehalt |
  | cu_content                 | Cu-Gehalt |
  | nb_content                 | Nb-Gehalt |
  | ti_content                 | Ti-Gehalt |
  | al_content                 | Al-Gehalt |
  | b_content                  | B-Gehalt |
  | yield_strength_mpa         | Streckgrenze |
  | tensile_strength_mpa       | Zugfestigkeit |
  | elongation_percent         | Dehnung |

- Removed duplicates using Excel’s 'Remove Duplicates' function.
- Fixed data types for columns (number, text) and corrected number formats.
- Removed incorrect entries (e.g., text in numerical columns).
- Handled missing values:
  - Replaced missing categorical values with 'unknown'.
  - Left numerical missing values as-is to allow for context-based replacement later.
- Converted data into a table for easier manipulation.

### 3. Preprocessing supplier_data_2
- Removed empty columns.
- Handled missing categorical data by filling with 'unknown' or 'null'.
- Standardized column data types.
- Converted data into a table for easier manipulation.

### 4. Merging Data
- Since no unique identifier exists in both datasets, merging was done based on common columns.
- Common columns between both files:
  
  | supplier_data_2 Column   | supplier_data_1 Column |
  |--------------------------|------------------------|
  | MATERIAL_NAME           | material_quality |
  | NOMINAL_THICKNESS_MM    | nominal_thickness_mm |
  | WIDTH_MM                | width_mm |

- Given the small dataset size (~100 records per file), the simplest approach was to manually append data.
- The final merged dataset was saved as **combined_supplier_data**.

Alternatively, both tables could have been merged while keeping all fields, with missing fields filled in with null values accordingly. However, I did not take this approach due to limited context available.






