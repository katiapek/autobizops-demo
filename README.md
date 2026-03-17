![Python](https://img.shields.io/badge/Python-3.11-blue?logo=python)
![Flask](https://img.shields.io/badge/Flask-3.1.1-lightgrey?logo=flask)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-14.15-blue?logo=postgresql)
![Docker](https://img.shields.io/badge/Docker-28.3-blue?logo=docker)
# AutoBizOps Demo 

## Overview

Creating SEO content at scale is time-consuming and costly. AutoBizOps is a demo of a system I built to automate repetitive SEO and marketing workflows, saving teams hours of manual effort.

This app demonstrates how Python, APIs, and lightweight SaaS integrations can turn complex marketing processes into repeatable, automated pipelines.

Instead of managing keywords, briefs, and reports manually, AutoBizOps automates research, content preparation, and reporting — making it easier to scale SEO without scaling costs.

---

## Source Code

- **Full backend codebase:** [autobizops](https://github.com/katiapek/autobizops)

---

## Why It Matters

Marketing teams and agencies spend hundreds of hours doing repetitive SEO tasks. With AutoBizOps, I showed how these workflows can be:
- Automated → saving time & money
- Standardized → ensuring quality
- Scalable → supporting larger campaigns without more headcount

## Features
- Keyword Research Automation – scrape, clean, and cluster keyword data from multiple sources
- Content Brief Generator – create ready-to-use outlines for blog posts
- Workflow Orchestration – schedule and run pipelines with minimal human input

---

## Architecture


AutoBizOps follows a modular design so components can be swapped or scaled:
- Backend: Python (Flask) for APIs and task orchestration
- Data Layer: PostgreSQL for structured storage
- Integrations: n8n, Apify, AI Agents API's
- Automation: Celery for job queues, Redis for caching
- Containerization: Docker for deployment
- Frontend: Bootstrap 5.3, DataTables

![AutoBizOps Architecture](screenshots/automation_graph.png)

---

## Screenshots

| Home Page                            | User Account                        |
|--------------------------------------|-------------------------------------|
| ![Home](screenshots/automations.png) | ![Account](screenshots/account.png) |


| Login Page | Register Page |
|------------|---------------|
| ![Login](screenshots/login.png) | ![Register](screenshots/register.png) |

| Creating Post                                   | Pricing                             |
|-------------------------------------------------|-------------------------------------|
| ![Generate Post](screenshots/generate_post.png) | ![Pricing](screenshots/pricing.png) |


---

## Relationships

```mermaid
  erDiagram
    USERS ||--o{ GENERATED_BLOG_POSTS : "creates"
    AUTOMATIONS ||--o{ GENERATED_BLOG_POSTS : "powers"
    GENERATED_BLOG_POSTS ||--o{ BLOG_POST_ITERATIONS : "has"
    GENERATED_BLOG_POSTS ||--o{ BLOG_POST_CONTEXTS : "has"

    USERS {
        int id PK
    }

    AUTOMATIONS {
        int id PK
    }

    GENERATED_BLOG_POSTS {
        int id PK
    }

    BLOG_POST_ITERATIONS {
        int id PK
    }

    BLOG_POST_CONTEXTS {
        int id PK
    }
```

## Future Plans / Roadmap
- Live demo deployment
- AI-powered content evaluation
- Analytics dashboards
- Customer Support

---

## 📜 License

MIT

Demo code for educational/portfolio purposes only — do not use in production without permission.

---

