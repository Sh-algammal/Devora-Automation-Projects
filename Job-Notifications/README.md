# Job Notifications

An automated job collection and notification workflow built with **n8n**, developed as part of Devora Community projects.

![n8n](https://img.shields.io/badge/Workflow-n8n-EA4B71)
![Source](https://img.shields.io/badge/Source-Wuzzuf-1B4F9C)
![Discord](https://img.shields.io/badge/Delivery-Discord-5865F2)
![Email](https://img.shields.io/badge/Delivery-Email-D14836)

---

## Table of Contents

- [Overview](#overview)
- [Workflow Process](#workflow-process)
- [Technologies Used](#technologies-used)
- [Requirements](#requirements)
- [Setup](#setup)
- [Security & Responsible Use](#security--responsible-use)
- [Limitations](#limitations)
- [About](#about)

---

## Overview

This workflow automates the collection of job listings from **Wuzzuf** and delivers formatted notifications through **Discord** and **email**.

It uses scheduled HTTP requests and HTML extraction to collect the available job information, so community members can follow new opportunities without checking the site manually.

---

## Workflow Process

```text
Schedule (every 3 hours) → HTTP Requests → HTML Extraction (CSS) → JavaScript Formatting → Message Splitting → Discord + Email
```

| # | Step | Description |
|---|---|---|
| 1 | **Trigger** | The workflow runs every three hours. |
| 2 | **Fetch pages** | HTTP requests are sent to the configured Wuzzuf search pages. |
| 3 | **Extract** | Job information is extracted from the HTML using CSS selectors. |
| 4 | **Format** | Collected listings are processed and formatted with JavaScript. |
| 5 | **Split** | Messages are split when needed to meet Discord's message limits. |
| 6 | **Discord** | Notifications are delivered to the configured Discord channel. |
| 7 | **Email** | Job updates are sent by email. |

---

## Technologies Used

| Category | Tools |
|---|---|
| Automation | n8n |
| Scripting | JavaScript (n8n Code nodes) |
| Collection | HTTP Requests, HTML Extraction, CSS Selectors |
| Delivery | Discord, Email |

---

## Requirements

- An active **n8n** instance (cloud or self-hosted).
- Internet access.
- A Discord integration (bot or webhook).
- A configured email service (SMTP or Gmail).

---

## Setup

1. **Import** `workflow.json` into n8n (*Workflows → Import from File*).
2. **Schedule:** configure the Schedule Trigger (default: every three hours).
3. **Search URLs:** review and configure the Wuzzuf search URLs for the roles and locations you want.
4. **Selectors:** verify the HTML extraction CSS selectors against the current page structure.
5. **Discord:** configure Discord credentials.
6. **Email:** configure email credentials.
7. **Test** the workflow manually and verify that both Discord and email notifications arrive correctly.

---

## Security & Responsible Use

- **Review the source website's terms of service and `robots.txt`** before automating collection, and make sure your use complies with them and with applicable regulations.
- **Be a polite client:** keep the request frequency reasonable, avoid unnecessary requests, and do not try to bypass rate limits or access controls.
- **Treat scraped content as untrusted.** Job titles and descriptions are third-party input. Sanitize them before posting, and neutralize unintended mentions (such as `@everyone` or `@here`) using Discord's `allowed_mentions` setting or by escaping them.
- **Discord webhook URLs and email credentials are secrets.** Store them in n8n credentials, never commit them, and review `workflow.json` for hard-coded values before sharing it.
- For email, use an app-specific password or OAuth instead of your main account password, and send only to intended recipients.

---

## Limitations

- Changes to the website's structure can break the CSS selectors and stop extraction.
- Job availability and accuracy depend entirely on the source website.
- **Deduplication is not guaranteed.** Unless you configure it, the same job may be sent repeatedly across runs. Consider tracking seen job URLs or IDs (for example in Google Sheets or n8n static data) to notify only about new listings.

---

## About

Developed by **@sh_algammal**.
