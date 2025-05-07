# 📬 Email-to-Google Sheet AI Summary Bot

This project is an automated **Email-to-Google Sheet pipeline** built with [n8n](https://n8n.io/), leveraging **OpenAI's GPT-4o** for summarization and action item extraction. It monitors your Gmail inbox for new messages, summarizes the email using LLMs, and logs structured data to a Google Sheet.

🔗 **Watch the Demo Video:** [YouTube - Email to Sheet AI Summary Bot](https://www.youtube.com/watch?v=s0XWcKi3qI0)

---

## 🚀 Features

- 🔔 Triggers automatically when a new Gmail email is received
- 📬 Extracts email `sender`, `subject`, and `body`
- 🧠 Sends the body to OpenAI GPT-4o to:
  - Summarize the email in **3 sentences**
  - Extract **action items** (if any)
- 📊 Logs the following into Google Sheets:
  - Sender
  - Subject
  - Summary (from GPT)
  - Action Items (from GPT)
  - Timestamp

---

## 🧩 Workflow Overview

### 1. **Gmail Trigger (Polls every 1 minute)**
   - Configured to detect new unread emails.

### 2. **Extract Email Data**
   - Formats and prepares `From`, `Subject`, `Body` fields for further processing.

### 3. **OpenAI GPT-4o Node**
   - Sends the email body with this prompt:
     ```
     Summarize this email in 3 sentences, and extract action items (if any).
     ```
   - Returns structured JSON with `summary` and `action_items`.

### 4. **JSON Parser**
   - Parses GPT-4o response into clean, structured fields.

### 5. **Google Sheets Integration**
   - Appends a new row with:
     - Sender
     - Subject
     - Summary
     - Action Items
     - Timestamp

---

## 📁 Files

- `Email_to_Sheet_AI_Summary_Bot.json`: Exported n8n workflow file (⚠️ Requires your own Gmail, OpenAI, and Google Sheets credentials to run)

---

## 📽 Demo Preview

Watch a full walkthrough of the project, execution, and output:
👉 [Demo](https://www.youtube.com/watch?v=s0XWcKi3qI0)

---

## 🛠 Requirements

- A Gmail account
- Google Sheets access and API credentials
- OpenAI API key (GPT-4o access)
- n8n self-hosted or cloud account

---

## 📌 Notes

- You can adjust the polling interval based on your workflow needs.
- Ensure proper credentials are securely stored (not hardcoded) when deploying this at scale.

---

## 🧠 Author

Made with ❤️ by Me – feel free to connect and ask questions!
