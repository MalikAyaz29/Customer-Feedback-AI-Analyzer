# 🤖 Customer Feedback AI Analyzer

> An n8n automation that turns raw customer feedback into actionable insights — automatically.

[![n8n](https://img.shields.io/badge/Workflow-n8n-orange?logo=n8n)](https://n8n.io/)
[![AI](https://img.shields.io/badge/AI-OpenAI-black?logo=openai)](https://openai.com/)
[![Google Sheets](https://img.shields.io/badge/Storage-Google%20Sheets-34A853?logo=google-sheets)](https://www.google.com/sheets/about/)
[![Gmail](https://img.shields.io/badge/Notification-Gmail-EA4335?logo=gmail)](https://www.gmail.com/)

## 📌 Overview

Customer feedback is valuable, but manually reading, categorizing, and summarizing every response can be time-consuming.

This project automates that process using **n8n + an AI Agent**.

A customer submits feedback through a form, the AI analyzes and summarizes it, the result is stored in Google Sheets, and a notification containing the AI-generated analysis is sent by Gmail.

### ⚡ Workflow at a glance

```text
┌──────────────────────┐
│   Customer Feedback  │
│        Form          │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│      🤖 AI Agent     │
│                      │
│  • Sentiment         │
│  • Category          │
│  • Summary           │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│   📊 Google Sheets   │
│                      │
│  Store feedback +    │
│  AI analysis         │
└──────────┬───────────┘
           │
           ▼
┌──────────────────────┐
│      📧 Gmail        │
│                      │
│  Send AI analysis    │
│  notification        │
└──────────────────────┘
```

---

## ✨ Features

- 📝 **Feedback Collection** — Collects customer name, email, and feedback through an n8n form.
- 🧠 **AI Analysis** — Uses an OpenAI-powered AI Agent to process the submitted feedback.
- 😊 **Sentiment Analysis** — Classifies feedback as **Positive, Negative, or Neutral**.
- 🏷️ **Category Detection** — Categorizes feedback into:
  - Product
  - Delivery
  - Customer Service
  - Pricing
  - Other
- ✍️ **Automatic Summarization** — Generates a concise one-to-two sentence summary.
- 📊 **Google Sheets Storage** — Saves the original feedback and AI-generated summary.
- 📧 **Email Notification** — Sends the AI-generated analysis through Gmail.
- 🔄 **End-to-End Automation** — Once feedback is submitted, the entire process runs automatically.

---

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| **n8n** | Workflow automation & orchestration |
| **OpenAI** | AI-powered feedback analysis |
| **Google Sheets** | Store feedback and analysis |
| **Gmail** | Send automated notifications |

---

## 🔄 How It Works

### 1. 📝 Form Submission

The workflow starts when a customer submits the feedback form.

The form collects:

- Customer name
- Customer feedback
- Customer email

### 2. 🤖 AI Agent

The feedback is passed to the AI Agent.

The Agent is instructed to produce:

```text
Sentiment: Positive / Negative / Neutral
Category: Product / Delivery / Customer Service / Pricing / Other
Summary: Concise summary of the feedback
```

### 3. 📊 Google Sheets

The workflow then appends the information to a Google Sheet.

Example:

| Name | Email | Body | Summary |
|---|---|---|---|
| John | john@example.com | Delivery was very late. | Customer is dissatisfied with the delayed delivery. |

### 4. 📧 Gmail

The AI-generated analysis is then sent through Gmail so the responsible team can review the feedback without manually checking the spreadsheet.

---

## 📁 Project Structure

```text
customer-feedback-analyzer/
│
├── workflow.json
└── README.md
```

`workflow.json` contains the exported n8n workflow.

---

## 🚀 Getting Started

### Prerequisites

You'll need:

- An n8n instance/account
- An OpenAI credential
- A Google Sheets account
- A Gmail account

### Import the workflow

1. Open your n8n workspace.
2. Import `workflow.json`.
3. Reconnect your credentials:
   - OpenAI
   - Google Sheets
   - Gmail
4. Configure your Google Sheet.
5. Replace any placeholder values such as:

```text
YOUR_GOOGLE_SHEET_ID
YOUR_EMAIL@example.com
```

6. Test the workflow by submitting feedback through the form.
7. Verify the result in Google Sheets and Gmail.

> 🔐 **Security:** Credentials are intentionally not included in this repository. Configure your own credentials after importing the workflow.

---

## 🧪 Example

### Input

```text
The product is really good, but my order arrived three days late.
Customer service also took a long time to respond.
```

### AI Output

```text
Sentiment: Negative
Category: Delivery
Summary: The customer likes the product but is dissatisfied with the delayed delivery and slow customer service response.
```

### Result

The original feedback and AI-generated summary are stored in Google Sheets, while the AI analysis is sent through Gmail.

---

## 🎯 What This Project Demonstrates

This project demonstrates practical knowledge of:

- n8n workflow design
- Form triggers
- AI Agent integration
- Prompt engineering
- Expression mapping
- LLM-powered text analysis
- Google Sheets integration
- Gmail integration
- Multi-step workflow orchestration
- Automated data processing

---

## 🔮 Future Improvements

Possible next steps for this workflow:

- [ ] Add a **priority score** (Low / Medium / High)
- [ ] Use a **Structured Output Parser** for cleaner AI results
- [ ] Add an **IF/Switch node** for different actions based on sentiment
- [ ] Send urgent negative feedback to a separate notification channel
- [ ] Create a dashboard for feedback trends
- [ ] Store feedback in a database instead of only Google Sheets
- [ ] Add persistent customer conversation memory where appropriate
- [ ] Add error handling and retry logic

---

## 📚 Learning Goal

This project was built as a practical introduction to **n8n workflow automation and AI-powered orchestration**.

The main architectural idea is simple:

```text
AI = Analyze & Generate
n8n = Orchestrate & Automate
```

---

## 👨‍💻 Author

**Muhammad Ayaz Rafique**

Built as part of my journey into **AI Automation, RAG, and Agentic AI**.

---

## ⭐ If You Find This Useful

Feel free to explore the workflow, modify it, and build your own version.
