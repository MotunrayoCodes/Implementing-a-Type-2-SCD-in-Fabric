# Implementing-a-Type-2-SCD-in-Fabric

 Overview
This project implements a Type 2 Slowly Changing Dimension logic to track historical employee data using PySpark within a Microsoft Fabric notebook.

🛠 Here’s a quick breakdown of the workflow:

1. Uploaded and converted the raw dataset to a Delta table
2. Cleaned the data:
   - Converted LoadDate column to proper Date type.
   - Filled nulls in LoadDate with current date using coalesce()
   - Removed duplicates.
3. Created an empty dimension table to track historical employee data.
4. Applied SCD2 logic using window functions:
    - Set StartDate from LoadDate.
    - Used lead() to compute EndDate.
    - Marked current records with IsActive = Yes.
5. Dropped temporary columns and saved final output to dim_employee with schema overwrite enabled.

<img width="849" height="463" alt="final_employee table" src="https://github.com/user-attachments/assets/e75e917f-1c3e-496b-8368-591128df0a73" />

