# Automated-SLA-Alarm-Reporting-System
## SLA & Alarm Data Processing Tool (Sample Project)

A sanitized demonstration project built with Python, Tkinter, Pandas & PostgreSQL

# Overview

This project is a desktop-based data processing tool that automates key SLA (Service-Level Agreement) data workflows such as:

Loading meter master data from Excel

Filtering and validating input data

Connecting to a PostgreSQL database

Fetching SLA-related metrics in batches

Exporting results into clean Excel reports

Providing real-time logs and user feedback

This is a GitHub-safe sample version — all sensitive information (IP, credentials, client structures, production SQL) has been removed and replaced with placeholders/environment variables.

 Key Features
🔹 1. Interactive Tkinter UI

Load Excel master data

Clean and validate meter numbers

Trigger SLA data extraction

Real-time logs displayed inside the GUI

🔹 2. Excel-Based Workflow

Accepts .xlsx / .xls files

Validates presence of required meter_number column

Applies basic data filtering

🔹 3. Database Connectivity (Secure)

Uses PostgreSQL + psycopg2

DB credentials are read via environment variables:

DB_HOST, DB_PORT, DB_NAME, DB_USER, DB_PASSWORD


(No hard-coded credentials)

🔹 4. Batch-Based SQL Execution

Avoids large IN queries

Automatically splits meter list into batches of configurable size

Merges and exports all results

🔹 5. Excel Output

All results exported as:

SLA_Output_YYYYMMDD_HHMMSS.xlsx

🔹 6. Logging System

Timestamps

Status messages

Error handling

Everything visible inside the UI.

# Tech Stack
Component	Technology
GUI	Tkinter
Backend	Python
Database	PostgreSQL
Data Handling	Pandas
Exports	Excel (OpenPyXL)
Security	.env variables
📁 Project Structure
├── sla_app.py               # main application file
├── README.md                # documentation
├── sample_data.xlsx         # demo input file (optional)
└── .env                     # environment variables (not committed)

⚙️ Environment Setup
1️⃣ Install dependencies
pip install pandas psycopg2 python-dotenv openpyxl

2️⃣ Create a .env file
DB_HOST=localhost
DB_PORT=5432
DB_NAME=sample_db
DB_USER=your_user
DB_PASSWORD=your_password


⚠️ Never commit .env.

▶️ How to Run the Application
python sla_app.py


GUI will launch automatically.

# How It Works Internally
Step 1 – Load Excel

User uploads a file containing meter numbers.

Step 2 – Filter Data

Removes blanks

Removes duplicates

Prepares clean list for SQL

Step 3 – Build SQL Query

Each batch generates a query like:

SELECT meter_number, sample_col1, sample_col2
FROM sample_table
WHERE meter_number IN (...)

Step 4 – Fetch in Batches

Default batch size: 500

Results appended to the list

Step 5 – Create Final Output File

Outputs to timestamped Excel.

🧪 Sample Output

File generated:

SLA_Output_20250101_153045.xlsx


Columns included:

meter_number

col1

col2

📜 Disclaimer

This project is a sanitized educational sample.
The real production version contains:

deeper SLA logic

Alarm analytics

Multiple modules (BLP, DLP, Billing, MDM)

Complex SQL

Consolidated dashboards

All sensitive logic has been intentionally removed.

🙌 Author

Manish
Python Developer • Smart Metering • Analytics Automation
Feel free to fork, use, or improve the project.
