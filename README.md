# Data Cleaning and Transformation Using Power Query

## Project Overview

This project demonstrates the use of Power BI and Power Query to transform a poorly structured ecological survey spreadsheet into a clean, standardised and consolidated dataset suitable for further analysis.

The primary objective was to practise practical data cleaning, transformation, data validation and evidence-based decision-making.

## Data Source

- **Dataset:** Portal Project Teaching Database – Messy Survey Data
- **Provider:** Data Carpentry
- **Source:** https://datacarpentry.github.io/spreadsheet-ecology-lesson/
- **Original worksheets:** 2013, 2014 and Dates

## Tools Used

- Microsoft Power BI Desktop
- Power Query
- Microsoft Excel
- GitHub

## Initial Data Quality Challenges

The original dataset contained several structural and data-quality issues:

- Multiple survey plots arranged horizontally and vertically within worksheets.
- Inconsistent column names and capitalisation.
- Unnecessary headers, blank rows and separator columns.
- Combined species and sex information.
- Incomplete and inconsistent date formats.
- Numeric measurements containing text annotations.
- Unreliable weight measurements due to uncalibrated equipment.
- Potential duplicate observations across worksheets.
- Conflicting collection dates.

## Data Cleaning and Transformation Process

### 1. Data Restructuring

- Created reference queries to isolate individual survey plots.
- Removed unnecessary rows and columns.
- Promoted appropriate column headers.
- Added plot identifiers to preserve the origin of each observation.

### 2. Data Standardisation

- Standardised column names and data types.
- Split combined species and sex values using delimiters.
- Corrected incomplete dates using the appropriate year and locale settings.
- Standardised the structure of individual plot tables before consolidation.

### 3. Data Quality Management

- Preserved genuine missing values rather than introducing unsupported replacements.
- Replaced unreliable weight measurements with null values while retaining other observation details.
- Identified questionable collection dates and retained the original values pending source verification.

### 4. Data Consolidation

- Appended individual plot queries into consolidated worksheet tables.
- Combined the cleaned 2013 and 2014 datasets into a single survey table.
- Disabled loading of intermediate queries to maintain an organised data model.

### 5. Data Validation and Reconciliation

Used Left Anti and Right Anti Joins to compare the additional Dates worksheet against the cleaned 2014 Plot 3 dataset.

The comparison identified 12 matching rows and one conflicting collection date. The additional worksheet was not appended because it contained no confirmed new observations.

## Data Quality Decisions

| Issue | Decision | Rationale |
|---|---|---|
| Uncalibrated weighing equipment | Replace affected weights with null | Preserve reliable observation details without retaining unreliable measurements |
| Plot 4 dates recorded as 08/01/1978 | Retain original dates | Insufficient evidence to justify correction |
| Conflicting dates of 18/02/2014 and 19/02/2014 | Retain the primary worksheet date | Requires source verification |
| Additional Dates worksheet | Exclude from consolidation | Avoid introducing likely duplicate observations |
| Redundant Year column | Exclude | Year can be derived from the collection date |

## Final Dataset

The final consolidated dataset contains **88 records and 5 columns**.

| Column | Data Type |
|---|---|
| Date collected | Date |
| Species | Text |
| Sex | Text |
| Weight | Decimal Number |
| Plot | Whole Number |

## Project Deliverables

- **Survey_data.pbix** – Power BI file containing the cleaning and transformation steps.
- **Survey_Cleaned.csv** – Final cleaned and consolidated dataset.

## Skills Demonstrated

- Data cleaning and preparation
- Power Query transformations
- Data restructuring
- Date conversion and locale management
- Data standardisation
- Query referencing
- Appending and merging queries
- Anti Join comparisons
- Data validation and reconciliation
- Analytical reasoning and data-quality decision-making

## Key Learnings

This project reinforced the importance of understanding data before transforming it. Effective data cleaning involves more than correcting formatting issues; it requires evaluating data reliability, preserving valid information, investigating inconsistencies and avoiding unsupported assumptions.

## Project Scope

This project focuses exclusively on data preparation, cleaning and validation. Data analysis, visualisation and dashboard development are outside its scope.

## Project Status

Completed – with identified source-data discrepancies documented for future verification.
