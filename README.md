# Air Quality Data Ingestion to Snowflake

This repository automates the process of fetching air quality data from an API, storing it locally, and uploading it to Snowflake using Snowpark. The workflow is scheduled to run periodically using GitHub Actions.

## Features

Fetches air quality data from the India Data Portal API.

Saves the data as a JSON file with a timestamp.

Uploads the JSON file to a Snowflake stage.

Uses Snowpark for efficient data transfer and processing.

Automated execution via GitHub Actions.

## Prerequisites

Before running the script, ensure you have:

A Snowflake account with required permissions.

An API key from data.gov.in.

Python 3.8+ installed.

Required Python dependencies installed.

Setup Instructions

### 1. Clone the Repository

git clone https://github.com/sirigireddy-sunitha/Air-Quality-Prediction-using-Snowflake.git

cd india-air-quality-json

### 2. Install Dependencies

pip install -r requirements.txt

### 3. Configure Environment Variables

Create a .env file in the root directory and add your credentials:

SNOWFLAKE_ACCOUNT= your accout name

SNOWFLAKE_USER= your User name

SNOWFLAKE_PASSWORD=Your Password

API_KEY=579b464db66ec23bdd000001f4fbce1dd76e42915f2f8c470043b682

API_URL=https://api.data.gov.in/resource/3b01bcb8-0b14-4abf-b6f2-c1bfd384ba69

### 4. Run the Script Locally

python ingest-api-data.py

## GitHub Actions Workflow

The repository includes a GitHub Actions workflow (.github/workflows/main.yml) to automate the data ingestion process.

Triggering the Workflow

Manually via workflow_dispatch.

Can be scheduled using cron jobs (e.g., every 45 minutes).

## Workflow Steps

Checkout Code - Clones the repository.

Set Up Python – Installs the required dependencies.

Install Snowpark – Ensures Snowpark is available.

Run the Python Script – Fetches data and uploads it to Snowflake.

# File Structure

📂 india-air-quality-json
 
├── ingest-api-data.py #Python script to fetch and upload data

├── requirements.txt   #Dependencies

├── .github/workflows/main.yml #GitHub Actions workflow

├── README.md            # Documentation



## Future Improvements

Implement better error handling.

Encrypt sensitive credentials.

Add data validation checks before upload.

## License

This project is licensed under the MIT License.
