# Threads Auto-Posting Automation using n8n

## Project Overview

This repository contains an automated Threads posting workflow built using **n8n** and the **Threads API**.

The automation monitors Google Sheets for newly added post content, automatically creates and publishes Threads posts, logs execution activity, handles failures, and supports migration to another local PC.

The workflow was implemented as part of an AI Automation and Integration task and includes setup verification, execution logging, retry handling, and migration-ready documentation.

---

## Project Objectives

The automation was designed to:

* Automate posting content to Threads
* Monitor post submissions through Google Sheets
* Use Threads API authentication securely
* Handle execution logging and error tracking
* Send automatic failure notifications
* Support export/import migration to another local PC
* Document implementation for future employees or maintainers

---

## Workflow Overview

### Automation Flow

```text
Google Sheets Trigger
        ↓
Retrieve Credentials
        ↓
Create Threads Post
        ↓
Publish Threads Post
        ↓
Success Logging
        ↓
Error Handling + Email Notification
```

### Major Components

| Component             | Purpose                         |
| --------------------- | ------------------------------- |
| Google Sheets Trigger | Detect newly added post entries |
| Google Sheets         | Credential storage and logging  |
| Threads API           | Publish Threads content         |
| HTTP Request Node     | API communication               |
| Gmail API             | Failure notification            |
| Gemini AI Agent       | Credential verification         |

---

## Features Implemented

### 1. Automated Threads Posting

* Automatically publishes content to Threads
* Triggered by newly added spreadsheet rows

### 2. Google Sheets Integration

Used for:

* Post queue monitoring
* Credentials retrieval
* Success logs
* Error logs
* Verification records

### 3. Error Handling

Includes:

* Retry logic
* Failure logging
* Gmail notification alerts

### 4. Credential Verification Workflow

AI-assisted validation of:

* Account ID
* Threads App ID
* Use Case
* Display Name
* Setup completeness

### 5. Migration Ready

The workflow is structured for reuse on another local PC.

Supported migration activities:

* Workflow export/import
* Credential reconfiguration
* Token replacement
* Environment variable updates
* Final end-to-end testing

---

## Repository Structure

```text
Repository/
│── README.md
│
│── workflow/
│   └── threads-posting-workflow.json
│
│── docs/
│   ├── setup-configuration.md
│   ├── migration-guide.md
│   ├── verification-record.md
│   └── test-report.md
│
│── screenshots/
│   ├── workflow-overview.png
│   └── execution-test.png
```

---

## Workflow Logic

### Step 1 — Monitor New Post Entry

The workflow continuously checks Google Sheets for newly added rows.

Trigger:

* Google Sheets Trigger
* Event: Row Added

Purpose:

* Detect newly submitted post content.

---

### Step 2 — Retrieve Credentials

Credentials are retrieved dynamically from Google Sheets.

Examples:

* Threads Access Token
* Threads ID

Purpose:

* Avoid hardcoded credentials.

---

### Step 3 — Create Threads Post

The workflow sends an authenticated API request to create a Threads post container.

Method:

* HTTP POST

Purpose:

* Prepare content for publishing.

---

### Step 4 — Publish Threads Post

The workflow publishes the generated post.

Purpose:

* Make content live on Threads.

---

### Step 5 — Logging and Notifications

Successful executions:

* Logged to Google Sheets

Failures:

* Logged automatically
* Gmail notification triggered

---

## Testing Summary

| Test Item             | Result |
| --------------------- | ------ |
| Trigger Detection     | Passed |
| Credential Retrieval  | Passed |
| Threads Post Creation | Passed |
| Threads Publish API   | Passed |
| Retry Logic           | Passed |
| Error Handling        | Passed |
| Gmail Notification    | Passed |

---

## Migration Notes

To migrate this workflow to another PC:

1. Import workflow JSON into n8n
2. Reconnect Google OAuth credentials
3. Reconnect Gmail OAuth
4. Update Threads access tokens
5. Verify spreadsheet permissions
6. Run end-to-end posting test

---

## Deliverables

This repository includes:

* n8n Workflow JSON
* Setup & Configuration Documentation
* Migration Guide
* API Verification Record
* Test Report

---

## Status

**Completed**

Workflow implemented, tested, documented, and prepared for migration.

---

## Author

AI Automation and Integration Task Submission
