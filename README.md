# n8n My Bots

This repository contains my personal collection of **n8n automation workflows** (bots).  
I use them for email processing, data collection, Google Sheets automation and other everyday tasks.

Each bot is stored as a separate **JSON workflow file** that can be imported into any self-hosted n8n instance.

---

## 📌 Workflow 1: Gmail → Google Sheets – Expense Tracker

**File:** `gmail-expenses-to-sheets.json`  
*(rename here if your file has a different name)*

### What this bot does

- Checks Gmail inbox for new emails with receipts (for example, purchase confirmations).
- Extracts key fields from the email:
  - date
  - sender / merchant
  - amount
  - currency
  - subject / description
- Appends a new row with this data to a Google Sheet.
- Helps to automatically build an expense tracking table without manual copy-paste.

### How to use this workflow

1. **Import into n8n**
   - Open your n8n instance.
   - Go to **Workflows → Import from file**.
   - Select `gmail-expenses-to-sheets.json` and import it.

2. **Configure credentials**
   - Open the node **"Check for new emails"** and connect your **Gmail / IMAP** credentials.
   - Open the node **"Add to Google Sheet"** and connect your **Google Sheets** credentials.
   - Choose your spreadsheet and sheet where new rows should be added.

3. **Run the bot**
   - Click **“Execute workflow”** to test it manually.
   - When everything works, switch the workflow from **Inactive** to **Active** so it runs automatically.

### Security note

- Workflow JSON files do **not** contain any passwords or API tokens.
- All credentials are stored only in your own n8n instance.

---

## 🔧 Adding more bots

For each new workflow I will:

1. Export it from n8n as a `.json` file.
2. Add the file to this repository.
3. Document it in this README under a new section:

```text
## 📌 Workflow N: Name

File: `file-name.json`

What it does:
- ...

How to use:
- ... ```
```

Author: Nikita Marshchonok
