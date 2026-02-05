# Simple Booking Automation

Booking Management Automation System

## Overview

This project automates the processing of booking reservations by integrating data from Google Sheets. The system reads booking requests from an Inbox sheet, matches them with location-specific booking numbers, and outputs consolidated information for further processing.

## Problem Statement

The client receives booking reservations with location details that need to be matched with corresponding booking numbers and contact information. Manual processing is time-consuming and error-prone, especially when handling multiple requests.

## Solution

A Python-based automation script that:

- Connects to Google Sheets using the gspread API
- Reads data from three worksheets: Location, Inbox, and Output
- Merges inbox requests with location data based on matching locations
- Maintains historical records by appending to existing output data
- Removes duplicate entries automatically
- Updates the Output sheet with consolidated results

## Prerequisites

- Python 3.x
- Google Cloud Platform service account with Google Sheets API access
- Service account credentials file (keys.json)

## Required Python Libraries

```python
pip install gspread pandas
```

## Setup

1. Create a Google Cloud Platform project
2. Enable Google Sheets API
3. Create a service account and download credentials as keys.json
4. Place keys.json in the project root directory
5. Share your Google Sheet with the service account email

## Google Sheets Structure

### Location Sheet
Required columns:
- Location
- Booking Number

### Inbox Sheet
Required columns:
- Location
- Contact

### Output Sheet
Automatically populated with merged data from Location and Inbox sheets.

## How It Works

1. Authenticates with Google Sheets using service account credentials
2. Loads data from Location, Inbox, and Output worksheets
3. Validates that required columns exist in the source sheets
4. Merges Inbox data with Location data based on the Location column
5. Appends new merged data to existing Output data
6. Removes duplicate records
7. Clears and updates the Output sheet with the consolidated results

## Usage

Run the script using Jupyter Notebook:

```bash
jupyter notebook Script.ipynb
```

Or execute the notebook cells directly in VS Code.

## Current Limitations

- Requires manual execution (not automated on a schedule)
- Limited error handling for API rate limits
- No email integration yet

## Future Enhancements

- Email parsing integration
- Automated scheduled execution
- Message dispatch to contacts
- Slack/Teams notification integration
- Customer support chatbot
- Detailed analytics and reporting

## Collaborators

This project is being developed by Nqobile Muyambiri and Craig M.


