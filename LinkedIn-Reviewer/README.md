# LinkedIn Reviewer

An AI-powered LinkedIn profile evaluation workflow built with **n8n** and **Google Gemini**, developed as part of Devora Community projects.

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

LinkedIn Reviewer automates the evaluation of LinkedIn profiles by analyzing submitted profile information and generating structured feedback.

The workflow validates the submitted data, runs it through an AI-powered review pipeline, stores the evaluation results, and delivers a report to your team.

---

## Workflow Process

```text
Submission → JavaScript Validation → Gemini AI Agent → Criteria Evaluation → Result Structuring → Google Sheets → Discord
```

| # | Step | Description |
|---|---|---|
| 1 | **Receive submission** | A LinkedIn profile submission is received. |
| 2 | **Validate input** | The submitted information is validated with JavaScript. |
| 3 | **AI processing** | An AI Agent powered by Google Gemini processes the profile data. |
| 4 | **Evaluate** | The profile is assessed against the configured review criteria. |
| 5 | **Structure results** | The evaluation is formatted into a consistent, structured output. |
| 6 | **Store results** | Results are saved to Google Sheets. |
| 7 | **Deliver report** | The review report is sent through Discord. |

---

## Technologies Used

| Category | Tools |
|---|---|
| Automation | n8n |
| AI | Google Gemini API |
| Storage | Google Sheets |
| Delivery | Discord |
| Scripting | JavaScript (n8n Code nodes) |

---

## Requirements

- An active **n8n** instance (cloud or self-hosted).
- A Google account with Google Sheets access.
- A **Google Gemini API** key.
- A Discord bot or webhook integration.

---

## Setup

1. **Import** `workflow.json` into n8n (*Workflows → Import from File*).
2. **Google Sheets:** configure your Google Sheets credentials.
3. **Gemini:** add your Google Gemini API credentials.
4. **Discord:** configure the Discord integration (bot or webhook).
5. **Connect data sources:** link the target spreadsheet and the submission source.
6. **Test** the workflow with sample profile information before activating it.

---

## Security & Privacy

Profile submissions contain personal and professional information.

- Use **sample or anonymized profiles** when developing and testing.
- **Never commit** API keys, tokens, webhook URLs, or real user data. Sanitize `workflow.json` before sharing it.
- **Validate and sanitize all input** before it reaches the AI Agent. Submitted text is untrusted and may contain prompt-injection attempts (for example, instructions hidden inside a profile summary). Keep the system prompt separate from user content and treat the model's output as data, not instructions.
- If the submission endpoint is a public webhook, protect it with authentication or a secret token and consider rate limiting.
- Restrict access to the Google Sheet and Discord channel to authorized reviewers only.
- Grant each credential the minimum scopes it needs.
- Profile data is sent to the Gemini API for processing. Make sure this complies with your privacy policy and with the submitter's consent.

---

## Limitations

- Evaluation quality depends on the completeness of the submitted information and on the configured AI instructions and review criteria.
- AI-generated feedback can be inaccurate or subjective. **Review it manually before making any professional decision.**

---

## About

Developed by **@sh_algammal**.
