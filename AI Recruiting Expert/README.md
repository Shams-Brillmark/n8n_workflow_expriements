# AI Recruiting Expert

This repository contains an n8n workflow designed to automate the candidate screening process using AI. The workflow analyzes candidates' qualifications against a predefined profile and stores the results in a Google Sheet.

## Workflow Overview

1. **Google Drive Trigger**: Monitors a specific Google Drive folder for new CV/Resume uploads.
2. **Google Drive**: Downloads the uploaded CV/Resume.
3. **Extract from File**: Extracts text from the CV/Resume.
4. **Personal Data**: Extracts personal information such as name, email, telephone, city, and birthdate.
5. **Qualifications**: Extracts educational qualifications, job history, and skills.
6. **Merge**: Combines the extracted personal data and qualifications.
7. **Summarization Chain**: Summarizes the candidate's information.
8. **Profile Wanted**: Defines the profile sought by the company.
9. **IT Expert**: Evaluates the candidate against the profile and provides a score and considerations.
10. **Google Sheets**: Appends the evaluation results to a Google Sheet.

## Nodes

- **Google Drive Trigger**: Triggers the workflow when a new file is created in a specific Google Drive folder.
- **Google Drive**: Downloads the file from Google Drive.
- **Extract from File**: Extracts text from the downloaded file.
- **Personal Data**: Extracts personal information from the text.
- **Qualifications**: Extracts qualifications, job history, and skills from the text.
- **Merge**: Merges the extracted data.
- **Summarization Chain**: Summarizes the candidate's information.
- **Profile Wanted**: Sets the profile requirements for the job.
- **IT Expert**: Evaluates the candidate and provides a score and considerations.
- **Google Sheets**: Appends the evaluation results to a Google Sheet.

## Setup

1. **Google Drive**: Configure the Google Drive Trigger and Google Drive nodes with your Google Drive credentials.
2. **Google Sheets**: Configure the Google Sheets node with your Google Sheets credentials.
3. **OpenAI**: Configure the OpenAI nodes with your OpenAI API credentials.

## Usage

1. Upload a CV/Resume to the specified Google Drive folder.
2. The workflow will automatically trigger and process the CV/Resume.
3. The evaluation results will be appended to the specified Google Sheet.