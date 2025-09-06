# PAN Card Validation in SQL | Data Cleaning & Validation Project

This project demonstrates real-world data cleaning and validation of Indian PAN (Permanent Account Number) card numbers using **PostgreSQL SQL scripts**. It covers common tasks performed in data engineering projects such as data cleansing, validation, and reporting.

## 🚀 Objective

You are tasked with cleaning and validating a dataset containing Indian PAN numbers. The goal is to ensure that each PAN number adheres to the official format and categorize them as either **Valid** or **Invalid**.

## ✅ Key Features

- **Format Checking with Regex**  
  Ensure PAN numbers follow the official pattern:  
  `^[A-Z]{5}[0-9]{4}[A-Z]$`

- **Handling Missing Values**  
  Identify and handle rows where the PAN number is missing or incomplete.

- **Duplicate Removal**  
  Remove duplicate PAN numbers from the dataset.

- **Trimming Spaces & Correcting Case**  
  Remove leading/trailing spaces and convert all characters to uppercase.

- **Validation of Adjacent Repetitions & Sequences**  
  - No adjacent characters should be identical (e.g., `AABCD` is invalid).
  - No sequential alphabets in the first five characters (e.g., `ABCDE` is invalid).
  - No sequential digits in the next four characters (e.g., `1234` is invalid).

- **Categorization into Valid/Invalid PANs**  
  Classify PAN numbers based on the above validation rules.

- **Summary Report**  
  Provides:
  - Total records processed
  - Total valid PANs
  - Total invalid PANs
  - Missing or incomplete PANs

## 🧱 Database Setup

1. **Stage Table Creation**  
   Load the raw dataset into a staging table.

2. **Data Cleaning Process**  
   Normalize data by:
   - Removing spaces
   - Converting to uppercase
   - Removing duplicates
   - Handling missing values

3. **Validation Functions**  
   - `fn_check_adjacent_repetition(text) RETURNS boolean`  
     Checks for adjacent repetitive characters.
   - `fn_check_sequence(text) RETURNS boolean`  
     Checks for sequential characters.

4. **Final Categorization View**  
   A view `vw_valid_invalid_pans` provides a clear list of PAN numbers classified as Valid or Invalid.

5. **Summary Report Generation**  
   A final report shows overall statistics of the PAN validation process.

## ✅ Example Valid PAN
# Pan-Number-Validation-Project-using-SQL

## 📊 Usage

- Clone this repository.
- Use PostgreSQL to execute the SQL scripts provided.
- Load your PAN numbers dataset into the `stg_pan_numbers_dataset` table.
- Execute the scripts in the given order to get a clean dataset, perform validations, and generate reports.

## 📁 Dataset

The dataset is provided separately as an Excel file:  
`PAN Number Validation Dataset.xlsx`

## 📊 Example Summary Report

| TOTAL PROCESSED RECORDS | TOTAL VALID COUNT | TOTAL INVALID COUNT | TOTAL MISSING PANS |
|-------------------------|-------------------|---------------------|-------------------|
| 10000                   | 3193              | 5832                | 975               |

## 📋 Sample PAN Validations Output

| Pan_Number | Status  |
|------------|---------|
| VGLOD3180G | Valid   |
| PHOXD7232L | Valid   |
| MGEPH6532A | Valid   |
| JJCHK4574O | Invalid |
| XTQIJ2330L | Invalid |
| HTJYM3835H | Valid   |
| YQTAP6661X | Invalid |
| HVOFE5635Y | Valid   |
| HYUIJ7902R | Valid   |
| IDSMT3429E | Valid   |
| ABKJN5176J | Valid   |
| VUCZU0860T | Valid   |
| HZVMG3577F | Invalid |
| OWUIS0525P | Valid   |
| ETVSQ2345L | Valid   |
| TWNGF1358L | Valid   |
| OUPMW5639M | Valid   |
| TLVFA0299E | Invalid |
| DOURT5035Y | Invalid |
| GAVCQ1260C | Valid   |
| IMJQF4986W | Valid   |
| GZLLP1469G | Invalid |
| POTPT8630S | Valid   |
| HUAYW0019Y | Invalid |
| QHVER2630M | Valid   |
| HJLWW1202H | Invalid |
| XVRUI1629V | Valid   |
| ILFQO0021U | Invalid |
| LSJNM0572P | Valid   |
| ZPJQS1155M | Invalid |

## 📚 Learn More

This project is part of a hands-on data engineering project demonstrating real-world data cleaning and validation processes using SQL.

---

Feel free to contribute, raise issues, or suggest improvements!

## ⚖️ License

This project is licensed under the MIT License.
