# 🤖 AI News Automation Agent (n8n Workflow)

## 📌 Overview

This project is an automated **AI news aggregation and summarization system** built using **n8n**. It fetches the latest AI-related news, filters duplicates using historical logs, formats the results, and delivers a clean daily digest via email.

The workflow combines **AI search (Perplexity)**, **LLM processing (OpenAI GPT)**, and **Google Sheets memory** to create a lightweight **Retrieval-Augmented Generation (RAG) pipeline**.

---

## ⚙️ Features

* 📰 Fetches latest AI news (last 24 hours)
* 🧠 Uses AI to summarize and clean results
* 🔁 Removes duplicate news using historical logs
* 📊 Stores past news in Google Sheets
* 📧 Sends daily digest via Gmail
* ⏰ Runs automatically on a schedule (daily at 9 AM)

---

## 🧱 Architecture

```text
Schedule Trigger
      ↓
Perplexity (AI Search)
      ↓
OpenAI (Filter + Deduplicate + Format)
      ↓
Gmail (Send Email)
      ↓
Google Sheets (Store History)
```

---

## 🧠 How It Works

### 1. **Data Retrieval (Perplexity)**

* Queries recent AI news
* Focuses on major players:

  * OpenAI
  * Anthropic
  * Google DeepMind
  * Meta
  * Microsoft
  * xAI
  * Mistral
  * Hugging Face

---

### 2. **Processing (OpenAI GPT)**

* Converts raw search results into readable summaries
* Cross-checks against past news stored in Google Sheets
* Removes duplicates (even if worded differently)
* Formats output for readability

---

### 3. **Memory Layer (Google Sheets)**

* Stores:

  * Date
  * News summaries
* Used to:

  * Prevent repetition
  * Track historical AI developments

---

### 4. **Delivery (Gmail)**

* Sends a structured daily digest email
* Includes:

  * Clean summaries
  * Source URLs
  * Key insights

---

## 🧪 Example Output

```
Here's today's AI development news...

OpenAI released major upgrades to GPT models’ reasoning...
https://openai.com/blog/...

Anthropic improved Claude’s safety and reliability...
https://anthropic.com/...

Insight: AI labs are focusing on reasoning, reliability, and enterprise integration.
```

---

## 🔧 Setup Instructions

### 1. Requirements

* n8n (self-hosted or cloud)
* OpenAI API key
* Perplexity API key
* Google account (Sheets + Gmail)

---

### 2. Configure Credentials

#### 🔹 Perplexity

* Add API key
* Select model: `sonar-pro`

#### 🔹 OpenAI

* Use model: `gpt-5.2` (or equivalent available model)

#### 🔹 Google Sheets

* Provide spreadsheet ID
* Use sheet as historical log

#### 🔹 Gmail

* Connect via OAuth2

---

### 3. Google Sheets Structure

| Date       | Headlines          |
| ---------- | ------------------ |
| 2026-04-12 | AI news summary... |

---

### 4. Workflow Activation

* Set schedule trigger (e.g., 9 AM daily)
* Activate workflow in n8n

---

## 📁 Key Nodes Explained

| Node               | Purpose               |
| ------------------ | --------------------- |
| Schedule Trigger   | Runs workflow daily   |
| Perplexity Node    | Fetches AI news       |
| OpenAI Node        | Cleans + deduplicates |
| Google Sheets Tool | Reads past logs       |
| Gmail Node         | Sends email           |
| Append Sheet Node  | Saves new entries     |

---

## 🧠 Key Concepts

### 🔹 RAG (Retrieval-Augmented Generation)

* Retrieval → Perplexity (news search)
* Generation → OpenAI (summarization)

---

### 🔹 Deduplication Logic

* Compares new headlines with stored history
* Handles:

  * Reworded duplicates
  * Multiple sources reporting same news

---

## 🚀 Future Improvements

* Add relevance scoring filter
* Integrate better search APIs (Tavily / Brave)
* Add Slack / WhatsApp delivery
* Implement embeddings for smarter deduplication
* Store structured data instead of plain text

---

## 📌 Notes

* Uses mock/test data for development
* Ensure Google Drive API is enabled for sheet selection
* Use "By ID" for stable Google Sheets integration

---

## 👨‍💻 Author

Built by CJ Kakai
AI Automation | RAG Systems | Workflow Engineering

---

## ⭐ Summary

This project demonstrates:

* Real-world AI automation
* RAG system design
* Multi-tool orchestration using n8n

It’s a strong portfolio project for:

* AI Engineering
* Automation Engineering
* Backend / Workflow roles

---
