JSONPlaceholder Users → Google Sheets (n8n Scheduled Workflow)
Overview

This workflow automatically fetches user data from a public REST API and stores it in Google Sheets every hour.
It demonstrates scheduled automation, API integration, data transformation, and cloud storage using n8n.

Features

Scheduled execution every hour

REST API integration (JSONPlaceholder)

Data extraction and transformation (id, name, email)

Automatic insertion into Google Sheets

Error monitoring with optional Slack alerts

Workflow Architecture
Schedule Trigger (Hourly)
        ↓
HTTP Request (Fetch users)
        ↓
Transform Data (Extract fields)
        ↓
Google Sheets (Append rows)
        ↓
Error Check → Slack Notification (optional)

Nodes Description
1. Schedule Trigger

Runs the workflow automatically every hour to keep the dataset updated.

2. HTTP Request

Method: GET

Endpoint:

https://jsonplaceholder.typicode.com/users


Fetches user data in JSON format.

3. Data Transformation

Extracts required fields:

id

name

email

Formats the data for insertion into Google Sheets.

4. Google Sheets

Appends the transformed records into the selected spreadsheet.

5. Error Handling (Optional)

If the API request fails or returns an unexpected status code, a Slack notification can be triggered to alert the team.

Setup Instructions

Import the workflow JSON into n8n.

Connect your Google Sheets credentials.

Create a spreadsheet with columns:

id | name | email


Configure the Schedule Trigger (every 1 hour).

Activate the workflow.

Example Output (Google Sheets)
id	name	email
1	Leanne Graham	leanne@example.com

2	Ervin Howell	ervin@example.com
Use Cases

Automated data collection

ETL workflow demonstrations

API monitoring pipelines

Automation portfolio projects

Future Improvements

Deduplication (avoid inserting existing users)

Retry logic on API failure

Multi-sheet routing based on data rules

Dashboard reporting from collected data
