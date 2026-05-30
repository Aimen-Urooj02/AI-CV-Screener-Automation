# Multi-Platform Automation & AI CV Screener Pipelines

## Project Overview
This repository contains production-ready workflow setups built during the SkillSYNC N8N Launchpad workshops. The project bridges visual automation tools (**n8n** and **Make.com**) with Artificial Intelligence (**Gemini AI** and **OpenAI**) to create autonomous pipelines for customer inquiries, sentiment tracking, and high-volume recruitment screening.

---

## 🛠️ Tools & Technologies Connected
- **Automation Platforms:** n8n (Self-hosted/Local via Node.js & ngrok), Make.com
- **AI Integrations:** Gemini AI API, OpenAI API
- **Data Ingestion & Backends:** Google Forms, Google Sheets, Google Drive, Tally.so, Notion
- **Communication & Alerting:** Gmail

---

## 🚀 Detailed Workflow Architecture

### 1. AI-Powered CV Screener with Notion & Gmail (n8n Engine)
- **Objective:** Automate initial-round recruitment screening to save hours of manual review.
- **Pipeline Flow:** 1. **Google Sheets Trigger:** Monitors live form submissions from job applicants.
  2. **Data Extraction:** Fetches the matching uploaded CV binary from Google Drive via HTTP API requests.
  3. **JavaScript Transforms:** Cleans and formats the raw text layouts for evaluation nodes.
  4. **Gemini AI Engine:** Analyzes skill matrices against targeted job requirements and generates structured fit profiles.
  5. **Notion Sync:** Logs candidate cards, assigned metrics, and summary strings straight into a live "Talent Board".
  6. **Conditional Alerts:** Evaluates scores using an IF Node; candidates hitting a threshold score (e.g., 8/10) trigger an automated "Strong Candidate" alert email directly to the hiring manager.

### 2. Contact Form to Instant AI Reply (Make.com Engine)
- **Objective:** Instant customer engagement using generative AI responses.
- **Pipeline Flow:** Intercepts inbound customer queries submitted via Tally.so forms via webhooks, passes text structures directly to OpenAI's completion API to draft personalized answers, and instantly dispatches them via Gmail.

### 3. Smart Feedback Classifier (Make.com Engine)
- **Objective:** Dynamic routing based on structured feedback sentiment.
- **Pipeline Flow:** Catches digital satisfaction survey ratings, executes conditional routing logic (Positive vs. Negative sentiment channels), and fires targeted, contextual appreciation or resolution emails.

---

## 🧠 Key Technical Learnings & Challenges Overcome
- **Google OAuth & API Credentials:** Configured strict token authentication flows across Google Cloud Consoles and Notion Integration environments.
- **Dynamic Syntax Routing:** Mastered n8n item lists and expression scripting using `{{ $json.applicant_name }}` parameters to parse multi-node data streams smoothly.
- **Strict Data Engineering:** Controlled generative AI outputs to return reliable, structural JSON shapes to prevent processing breaks down the pipeline.
