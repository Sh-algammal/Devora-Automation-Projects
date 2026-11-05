# Devora Automation Projects

Practical, production-minded automation workflows built by **Devora Community**: AI-powered pipelines, process automation, data integration, and real-world problem solving.

This repository contains hands-on implementations built with **n8n**, **AI Agents**, **Google Gemini**, REST APIs, and web scraping, integrated with tools such as Discord, Google Sheets, Google Drive, and Email.

![n8n](https://img.shields.io/badge/Workflow-n8n-EA4B71)
![Gemini](https://img.shields.io/badge/AI-Google%20Gemini-4285F4)
![JavaScript](https://img.shields.io/badge/Code-JavaScript-F7DF1E)
![Status](https://img.shields.io/badge/Status-Active-success)

---

## Table of Contents

- [Projects](#projects)
- [Tech Stack](#tech-stack)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [Configuration](#configuration)
- [Security Notice](#security-notice)
- [Contributing](#contributing)
- [About Devora](#about-devora)

---

## Projects

| Project | Description | Delivery | Link |
|---|---|---|---|
| **CV Reviewer** | AI-powered CV analysis that generates structured feedback and an assessment report. | Report | [Open](./CV-Reviewer/) |
| **LinkedIn Reviewer** | Reviews LinkedIn profiles for completeness and professional presentation. | Report | [Open](./LinkedIn-Reviewer/) |
| **AI News & GitHub Trending** | Collects AI news and trending GitHub repositories, then posts formatted updates. | Discord | [Open](./AI-News-GitHub-Trending/) |
| **Job Notifications** | Collects job listings and notifies you about relevant opportunities. | Discord, Email | [Open](./Job-Notifications/) |

Each project folder contains an importable `workflow.json` and its own `README.md` with workflow details and requirements.

---

## Tech Stack

| Category | Tools |
|---|---|
| **Workflow Automation** | n8n |
| **AI & LLMs** | Google Gemini API, AI Agents |
| **Programming** | JavaScript (n8n Code nodes) |
| **APIs** | REST APIs, HTTP Requests, Webhooks |
| **Data Management** | Google Sheets, Google Drive |
| **Communication** | Discord, Email |
| **Data Collection** | RSS Feeds, Web Scraping |

---

## Repository Structure

```text
Devora-Automation-Projects/
├── CV-Reviewer/
│   ├── workflow.json
│   └── README.md
├── LinkedIn-Reviewer/
│   ├── workflow.json
│   └── README.md
├── AI-News-GitHub-Trending/
│   ├── workflow.json
│   └── README.md
├── Job-Notifications/
│   ├── workflow.json
│   └── README.md
└── README.md
```

---

## Getting Started

### Prerequisites

- A running **n8n** instance (cloud or self-hosted).
- Credentials for the services used by the workflow you choose (see the project's README), for example a Google Gemini API key, Google OAuth, or a Discord webhook.

### Steps

1. **Clone** the repository:
   ```bash
   git clone https://github.com/<your-org>/Devora-Automation-Projects.git
   cd Devora-Automation-Projects
   ```
2. **Pick a project** and read its `README.md` for requirements.
3. **Import** the project's `workflow.json` into n8n (*Workflows → Import from File*).
4. **Configure credentials** in n8n and attach them to the relevant nodes.
5. **Test** the workflow manually with sample data.
6. **Activate** it only after a successful test run.

---

## Configuration

Credentials are never stored in this repository. Create them inside n8n (*Credentials*) and select them in each node after importing.

Typical requirements across projects:

| Service | Used For |
|---|---|
| Google Gemini API | AI analysis and content generation |
| Google Sheets / Drive | Data storage and file access |
| Discord (webhook or bot) | Notifications and updates |
| Email (SMTP / Gmail) | Email delivery |

Refer to each project's README for the exact list.

---

## Security Notice

- **Never commit** API keys, access tokens, passwords, or private credentials.
- **Sanitize exports:** review `workflow.json` before committing or sharing it. Remove hard-coded secrets, webhook URLs, internal IDs, and personal data from node parameters and pinned data.
- **Use test data** when evaluating workflows that process personal information such as CVs and LinkedIn profiles.
- **Protect webhooks:** use authentication or secret tokens on any workflow exposed through a public webhook URL.
- **Apply least privilege:** grant API keys and OAuth scopes only the permissions the workflow needs, and rotate them if exposed.
- **Keep sensitive configuration and user data** outside the repository.

---

## Contributing

Contributions are welcome.

1. Fork the repository and create a feature branch.
2. Add or update the workflow along with its `README.md`.
3. Make sure no credentials or personal data are included in the export.
4. Open a pull request describing the workflow, its requirements, and how you tested it.

---

## About Devora

**Devora Community** is a programming and technology community that helps students learn, build practical projects, and develop industry-relevant technical skills.

This repository represents our practical work in AI integration and workflow automation.

---

**Built with curiosity. Automated with purpose.**

*Developed by Devora Community.*
