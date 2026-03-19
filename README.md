# Financial Analysis

This project automates the extraction of key financial statement data from annual report PDFs and uses a local LLM through Ollama to generate structured financial analysis.

It focuses on two main statements:

- Income Statement
- Balance Sheet

The script identifies the relevant pages in a PDF, extracts selected financial metrics, formats them into structured tables, computes derived values such as Gross Profit and Total Liabilities, and then sends the cleaned financial data to a locally hosted Mistral model for qualitative analysis.

---

## Features

- Detects Income Statement and Balance Sheet pages from PDF annual reports
- Extracts financial years automatically from the statement text
- Matches multiple aliases for each financial metric
- Pulls structured values for:
  - Revenue
  - Cost of goods sold
  - Gross Profit/(Loss)
  - Operating Result
  - Profit before income tax
  - Net Result
  - Total Assets
  - Total Liabilities
  - Total Equity
  - and more
- Calculates derived metrics such as:
  - Gross Profit/(Loss) = Revenue - Cost of goods sold
  - Total Liabilities = Total Current Liabilities + Total Non-Current Liabilities
- Converts extracted data into Pandas DataFrames
- Formats output into a readable financial statement layout
- Uses Ollama + Mistral to generate structured financial commentary in Chinese and English style sections:
  - Executive Summary
  - Red Flags
  - Forecast
  - Key Insights

---

## Project Workflow

The project follows this process:

1. Load a PDF annual report
2. Search for the Income Statement page
3. Search for the Balance Sheet page
4. Detect the financial years shown in each statement
5. Extract predefined financial line items using keyword matching
6. Store extracted values in dictionaries
7. Convert results into Pandas DataFrames
8. Calculate derived metrics
9. Print formatted financial statements
10. Send the structured data to a local Mistral model via Ollama for analysis

---

## Technologies Used

- Python
- pdfplumber
- regex (`re`)
- pandas
- requests
- tqdm
- threading
- Ollama
- Mistral

---

## File Structure

```bash
Financial_Analysis/
│
├── main.py
├── README.md
└── sample_reports/
