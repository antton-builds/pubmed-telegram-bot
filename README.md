# pubmed-telegram-bot
A Telegram bot that searches PubMed Central and delivers  AI-generated biomedical article summaries on demand.  Built with n8n, OpenAI, and NCBI EUtils API.
# PubMed Telegram Bot

A Telegram bot that lets you search and summarize biomedical 
research articles using plain language — no technical knowledge required.

## What it does

You send a message to a Telegram bot describing what you want to read about.
The bot searches PubMed Central, fetches the full articles, and sends you
a structured AI-generated summary for each one — directly in Telegram.

**Example message:**
> "why coffee makes you tired, last 5 years, 3 papers"

**What you get back:**
For each article the bot returns:
- Objective — what the study was trying to find out
- Methods — how the study was conducted
- Key Findings — the most important results
- Significance — why it matters
- Abbreviations — all technical terms explained
- Speculation — broader implications in plain language
- Limitations — what the study could not prove

---

## How it works

1. You send a research topic to the Telegram bot
2. An AI parses your message and builds a precise PubMed search query
   - The main topic is searched from article titles
   - The subtopic is searched from titles and abstracts
3. The query is sent to PubMed Central and matching articles are found
4. If nothing is found, the AI automatically expands the query
   using medical synonyms and tries again — up to 3 times
5. Each article is fetched in full and key sections are extracted
6. An AI summarizes each article individually
7. Summaries are delivered to you one by one in Telegram

---

## Requirements

- [n8n](https://n8n.io) — self-hosted or cloud
- Telegram Bot Token — create one via [@BotFather](https://t.me/botfather)
- OpenAI API key — for query parsing and summarization
- OpenRouter API key — for the summarization agent
- NCBI EUtils API — free, no key required (email address needed)

---

## Setup

1. Import the workflow JSON into n8n
2. Add your credentials:
   - Telegram Bot Token
   - OpenAI API key
   - OpenRouter API key
3. Set your Telegram Chat ID in the final node
4. Set your email address in the PubMed API nodes
5. Activate the workflow
6. Send a message to your bot and get started

---

## Data Sources

- **PubMed Central (NCBI EUtils API)** — free access to full biomedical articles

## Built With

- [n8n](https://n8n.io) — workflow automation
- [OpenAI GPT-4o-mini](https://openai.com) — query parsing
- [OpenRouter](https://openrouter.ai) — summarization agent
- [NCBI EUtils](https://www.ncbi.nlm.nih.gov/books/NBK25497/) — PubMed search and fetch

---

## License

MIT
