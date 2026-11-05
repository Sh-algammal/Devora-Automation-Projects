# AI News & GitHub Trending

An automated information collection and notification workflow built with **n8n**, developed as part of Devora Community projects.

![n8n](https://img.shields.io/badge/Workflow-n8n-EA4B71)
![GitHub API](https://img.shields.io/badge/Data-GitHub%20REST%20API-181717)
![RSS](https://img.shields.io/badge/Data-RSS-FFA500)
![Discord](https://img.shields.io/badge/Delivery-Discord-5865F2)

---

## Table of Contents

- [Overview](#overview)
- [Workflow Process](#workflow-process)
- [Technologies Used](#technologies-used)
- [Requirements](#requirements)
- [Setup](#setup)
- [Security Notes](#security-notes)
- [Limitations](#limitations)
- [About](#about)

---

## Overview

This workflow collects AI-related news and trending GitHub repositories, formats the retrieved information, and delivers scheduled updates to a Discord channel.

It helps community members stay informed about developments in Artificial Intelligence and open-source projects without checking multiple sources manually.

---

## Workflow Process

```text
Schedule Trigger ─┬─► VentureBeat AI RSS ──────┐
                  │                            ├─► JavaScript Formatting ─► Discord Messages ─► Discord Channel
                  └─► GitHub REST API ─────────┘
```

| # | Step | Description |
|---|---|---|
| 1 | **Trigger** | The workflow runs on a scheduled execution. |
| 2 | **AI news** | AI news is retrieved from the VentureBeat AI RSS feed. |
| 3 | **Trending repositories** | Trending GitHub repositories are fetched using the GitHub REST API. |
| 4 | **Process** | The collected data is cleaned and formatted with JavaScript. |
| 5 | **Prepare messages** | Discord-compatible messages are built. |
| 6 | **Deliver** | Updates are posted to the configured Discord channel. |

---

## Technologies Used

| Category | Tools |
|---|---|
| Automation | n8n |
| Scripting | JavaScript (n8n Code nodes) |
| Data sources | RSS Feeds, GitHub REST API |
| Networking | HTTP Requests |
| Delivery | Discord |

---

## Requirements

- An active **n8n** instance (cloud or self-hosted).
- Internet access.
- A Discord bot or webhook integration.
- GitHub API access where required (see [Security Notes](#security-notes)).

---

## Setup

1. **Import** `workflow.json` into n8n (*Workflows → Import from File*).
2. **Schedule:** configure the Schedule Trigger (frequency and timezone).
3. **RSS:** verify the RSS feed URL and node configuration.
4. **GitHub:** configure GitHub API access if required.
5. **Discord:** configure the Discord integration (bot or webhook).
6. **Test** the workflow manually and verify that messages are delivered correctly before activating the schedule.

---

## Security Notes

- **Discord webhook URLs are secrets.** Anyone with the URL can post to your channel. Store it in n8n credentials and never commit it.
- **GitHub token:** reading public repository data does not require special permissions. If you use a personal access token (for higher rate limits), use a fine-grained token with minimal or no scopes, and never commit it.
- **Treat external content as untrusted.** RSS titles, summaries, and repository descriptions come from third parties. Sanitize them before posting, and disable unintended mentions (such as `@everyone` or `@here`) by using Discord's `allowed_mentions` setting or by escaping them.
- **Respect Discord limits:** messages are capped at 2000 characters, so split or truncate long output.
- Review `workflow.json` for hard-coded secrets before sharing or publishing it.

---

## Limitations

- News and repository data depend on their external sources; changes to a feed or API can break the workflow.
- API rate limits (especially for unauthenticated GitHub requests) and source downtime may affect execution.
- GitHub does not provide an official "trending" API endpoint, so trending results are typically approximated through search queries. Results may differ from the trending page on github.com.

---

## About

Developed by **Devora Community**.
