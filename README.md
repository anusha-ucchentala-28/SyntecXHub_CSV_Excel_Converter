# SyntecXHub CSV to Excel Converter

A Python script to read CSV files, clean and normalize data, and export to Excel (.xlsx) format using pandas and openpyxl.

## Features

- **Data Cleaning**: Handles missing values by dropping rows with NaN.
- **Normalization**: Strips whitespace from column names and converts to lowercase.
- **Column Renaming**: Simple configurable column renaming.
- **Data Parsing**: Automatic date parsing for common date columns.
- **CLI Interface**: Command-line flags for input and output files.
- **Logging**: Informative logging and error messages for bad files.
- **Error Handling**: Graceful handling of file not found, empty files, and parsing errors.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/SyntecXHub_CSV_Excel_Converter.git
   cd SyntecXHub_CSV_Excel_Converter
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

## Usage

Run the script with input and output file paths:

```bash
python CSV_Excel_Converter -i input.csv -o output.xlsx
```

### Command-line Options

- `-i, --input`: Path to the input CSV file (required)
- `-o, --output`: Path to the output Excel file (.xlsx) (required)

### Example

```bash
python CSV_Excel_Converter -i data/sales.csv -o reports/sales_report.xlsx
```

## Data Processing Details

- **Missing Values**: Rows containing any missing values are dropped.
- **Column Names**: Leading/trailing whitespace is removed, and names are converted to lowercase.
- **Date Parsing**: Columns named 'date', 'created_at', or 'updated_at' are automatically parsed as dates.
- **Column Renaming**: Customize the `rename_dict` in the script for specific renames.

## Logging

The script provides detailed logging:
- INFO: Successful operations and data statistics
- WARNING: Non-critical issues (e.g., date parsing failures)
- ERROR: Critical errors that prevent completion

## Error Handling

- File not found: Logs error and exits
- Empty CSV: Logs error and exits
- Parsing errors: Logs warnings for non-critical issues, errors for critical ones

## Requirements

- Python 3.6+
- pandas
- openpyxl

## Troubleshooting

- Ensure the input CSV file exists and is readable.
- Check that the output directory is writable.
- For large files, ensure sufficient memory is available.
- If date parsing fails, verify date formats in the CSV.