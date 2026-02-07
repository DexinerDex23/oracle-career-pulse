👁️ Overview
This system operates as an end-to-end pipeline:

Extraction: Scrapes real-time LinkedIn job listings via Apify.

Neural Vetting: Processes job descriptions locally using Ollama (Llama 3.2) to assign a suitability score (0-10) based on a candidate's specific CV.

Data Persistence: Logs high-scoring leads into a central MasterPlan (Google Sheets).

Autonomous Drafting: Generates tailored, problem-solution oriented cover letters for top-tier opportunities.

🛠️ Tech Stack
Orchestration: n8n (Self-hosted/Cloud)

Neural Backend: Ollama running llama3.2:3b (Local execution for privacy)

Data Extraction: Apify (LinkedIn Jobs Scraper)

Storage: Google Sheets API

Environment: Optimized for Linux/Ubuntu 24.04 LTS

🚀 Getting Started
1. Prerequisites
An active n8n instance.

Ollama installed locally with the llama3.2 model pulled.

An Apify API Token.

A Google Cloud project with Sheets API enabled.

2. Installation
Clone this repository.

Open n8n and select Import from File.

Upload the workflow.json file provided in this repo.

3. Configuration
Apify Node: Create a new credential and paste your API Token.

Ollama Node: Ensure your Ollama service is reachable (usually http://localhost:11434).

Google Sheets Node: Connect your account and provide your target Spreadsheet ID.

The Brain (Scoring): Open this node and replace the [INSERT CV DATA] placeholder with your own professional profile/experience.

🔒 Security & Privacy
Local Processing: AI scoring and drafting are performed locally via Ollama. Your CV data never leaves your infrastructure to reach 3rd-party LLM providers.

Credentials: This workflow is sanitized. Never commit your .env files or hardcode API keys into the nodes before pushing back to GitHub.

📈 Philosophy
Systems over Motivation: Don't wait for the "mood" to apply. Let the system find the best fits while you sleep.

Leverage over Effort: Automate the noise (searching/filtering) so you can focus your energy on the signal (interviews/final negotiations).
