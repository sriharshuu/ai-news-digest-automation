# AI News Digest Automation with n8n and Google Gemini

## Overview

This project is an automated AI and technology news summarization workflow built with n8n. It collects articles from multiple RSS feeds, consolidates them into a single payload, summarizes the content using Google Gemini, and sends a structured digest by email through Gmail.

The workflow is designed to reduce the time spent manually tracking AI and technology news by turning multiple raw feeds into a concise daily briefing.

---

## Architecture

Schedule Trigger
      ↓
AI Business RSS ──┐
                  ├── Merge ──> Aggregate ──> Basic LLM Chain ──> Gmail
TechCrunch RSS ───┘                     │
                                        ↓
                              Google Gemini Chat Model
```

---

## Features

* Daily scheduled execution
* AI and technology news aggregation from multiple RSS sources
* Batch processing of article data
* Google Gemini-powered summarization
* Category-based digest generation:

* AI NEWS
* TECHNOLOGY UPDATES
* Automated email delivery through Gmail
* Prompt-driven structured output formatting

---

## Workflow Explanation

### 1. Schedule Trigger

Runs the workflow automatically at the configured time each day.

### 2. AI Business RSS

Fetches AI-focused news articles from the AI Business RSS feed.

### 3. TechCrunch RSS

Fetches broader technology news from TechCrunch.

### 4. Merge

Combines both RSS streams into a single workflow path.

### 5. Aggregate

Groups all articles into a single payload for LLM processing.

### 6. Basic LLM Chain

Sends the aggregated article data to Google Gemini with a custom prompt that:

* limits the response to provided content
* separates AI news and technology updates
* summarizes each item in 1–2 sentences
* includes source links

### 7. Gmail

Sends the final summarized digest as an email.

---

## Tech Stack

* **n8n** – workflow orchestration
* **Google Gemini** – AI summarization
* **RSS Feeds** – source content ingestion
* **Gmail** – email delivery

---

## RSS Sources

* AI Business RSS
* TechCrunch RSS

---

## Setup Instructions

### Prerequisites

* n8n instance (local or cloud)
* Google Gemini API key
* Gmail OAuth credentials
* Recipient email address

### Installation Steps

1. Import the workflow JSON into n8n.
2. Configure the Google Gemini credential in the Gemini Chat Model node.
3. Configure Gmail OAuth credentials in the Gmail node.
4. Replace `recipient@example.com` with your target email address.
5. Test the RSS nodes and LLM output.
6. Activate the workflow.

---

## Example Use Cases

* Personal AI news digest
* Daily technology briefing
* Startup intelligence monitoring
* Market research summaries
* Team knowledge automation

---

## Security Note

This repository does not include personal credentials, API keys, or OAuth secrets.
Before running the workflow, configure your own:

* Google Gemini API credentials
* Gmail OAuth credentials
* Recipient email address

---

## Future Improvements

* Add more RSS/news sources
* Deliver to Slack or Telegram
* Store summaries in Google Sheets / Notion / database
* Add article deduplication
* Add topic tagging or sentiment analysis
* Add per-category personalization

---

## Author

Built as an AI automation portfolio project using n8n, Gemini, RSS, and Gmail.
