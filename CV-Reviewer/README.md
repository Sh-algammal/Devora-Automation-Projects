# CV Reviewer

An AI-powered CV review automation built with **n8n** and **Google Gemini**, developed as part of Devora Community projects.

![n8n](https://img.shields.io/badge/Workflow-n8n-EA4B71)
![Gemini](https://img.shields.io/badge/AI-Google%20Gemini-4285F4)
![Discord](https://img.shields.io/badge/Delivery-Discord-5865F2)

---

## Table of Contents

- [Overview](#overview)
- [Workflow Process](#workflow-process)
- [Technologies Used](#technologies-used)
- [Requirements](#requirements)
- [Setup](#setup)
- [Security & Privacy](#security--privacy)
- [Limitations](#limitations)
- [About](#about)

---

## Overview

CV Reviewer automates the analysis of submitted CVs and produces structured evaluation reports.

The workflow receives CV submissions, extracts their content, runs the text through an AI analysis pipeline, and delivers the review results to your team.

---

## Workflow Process

```text
Google Form → Google Drive → PDF Text Extraction → Gemini AI Agent → Result Structuring → Google Sheets → Discord
```

| # | Step | Description |
|---|---|---|
| 1 | **Receive submission** | A CV is submitted through Google Forms. |
| 2 | **Retrieve file** | The uploaded CV is fetched from Google Drive. |
| 3 | **Extract text** | Text is extracted from the PDF file. |
| 4 | **AI analysis** | An AI Agent powered by Google Gemini evaluates the CV. |
| 5 | **Structure results** | The evaluation is processed into a consistent, structured format. |
| 6 | **Store results** | Review results are saved to Google Sheets. |
| 7 | **Deliver report** | The report is generated and sent through Discord. |

---

## Technologies Used

| Category | Tools |
|---|---|
| Automation | n8n |
| AI | Google Gemini API |
| Input | Google Forms |
| Storage | Google Drive, Google Sheets |
| Delivery | Discord |
| Scripting | JavaScript (n8n Code nodes) |

---

## Requirements

- An active **n8n** instance (cloud or self-hosted).
- A Google account with access to Forms, Drive, and Sheets.
- A **Google Gemini API** key.
- A Discord bot or webhook integration.

---

## Setup

1. **Import** `workflow.json` into your n8n instance (*Workflows → Import from File*).
2. **Google credentials:** configure Google Drive and Google Sheets credentials in n8n.
3. **Gemini:** add your Gemini API credentials.
4. **Discord:** configure the Discord integration (bot or webhook).
5. **Connect data sources:** link the Google Form and the target spreadsheet.
6. **Test** the workflow with a sample CV before activating it.

---

## Security & Privacy

CVs contain personal data (names, contact details, work history), so handle them carefully.

- Use **anonymized or test CVs** when developing and evaluating the workflow.
- **Never commit** API keys, tokens, webhook URLs, or real candidate data to the repository. Sanitize `workflow.json` before sharing it.
- Restrict access to the Google Drive folder, the Google Sheet, and the Discord channel to authorized reviewers only.
- Grant each credential only the minimum scopes it needs.
- Be aware that CV text is sent to the Gemini API for processing. Make sure this complies with your privacy policy and with candidates' consent.
- Consider a retention policy: delete stored CVs and results when they are no longer needed.

---

## Limitations

- The workflow depends on valid credentials and external integrations.
- Text extraction works on text-based PDFs; scanned or image-only CVs may produce poor or empty results.
- AI-generated feedback can be inaccurate or biased. **Always review it manually before making any recruitment decision.**

---

## About

Developed by **Devora Community**.
