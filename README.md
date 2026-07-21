# 🎬 AI Large Expense Tracker & Receipt Manager

![GitHub stars](https://img.shields.io/github/stars/belioautomation/AI-Large-Expense-Tracker-Receipt-Manager?style=for-the-badge)
![GitHub forks](https://img.shields.io/github/forks/belioautomation/AI-Large-Expense-Tracker-Receipt-Manager?style=for-the-badge)
![GitHub last commit](https://img.shields.io/github/last-commit/belioautomation/AI-Large-Expense-Tracker-Receipt-Manager?style=for-the-badge)
![GitHub repo size](https://img.shields.io/github/repo-size/belioautomation/AI-Large-Expense-Tracker-Receipt-Manager?style=for-the-badge)

An AI-powered expense automation workflow built with **n8n** that automatically processes receipts, extracts expense details using AI, stores structured expense records in Google Sheets, detects large expenses, sends real-time notifications, and archives processed receipts in Google Drive.

---

# 🚀 Features

* 📄 Automatic receipt detection from Google Drive
* 🤖 AI-powered receipt analysis
* 🔍 OCR text extraction from PDF and image receipts
* 💰 Automatic expense amount detection
* 🏪 Vendor recognition
* 📅 Receipt date extraction
* 🗂️ AI expense categorization
* 💳 Payment method detection
* 🧾 VAT/Tax extraction
* 📊 Automatic Google Sheets expense logging
* 🚨 Large expense detection using conditional workflow routing
* 📲 Telegram notifications for high-value expenses
* 📧 Gmail alerts for large expenses
* 📂 Automatic receipt archiving after successful processing

---

# 🏗️ Workflow Architecture

```text
Finance/
└── Incoming
        │
        ▼
Google Drive Trigger
        │
        ▼
Download Receipt
        │
        ▼
Extract From File (OCR)
        │
        ▼
AI Receipt Analyzer
(Google Gemini / OpenRouter)
        │
        ▼
Structured Output Parser
        │
        ▼
Normalize Values
(Code Node)
        │
        ▼
Google Sheets
(Expense Tracker)
        │
        ▼
IF (Amount > ₱5,000?)
     ├─────────────────────────┐
     │                         │
     ▼                         ▼
Telegram Alert          Move Receipt
     │                  to Processed
     ▼
Gmail Alert
     │
     ▼
Move Receipt
to Processed
```

---

# 🛠️ Technologies Used

* n8n
* Google Drive
* Google Sheets
* Google Gemini / OpenRouter
* OCR (Extract From File)
* JavaScript
* Telegram Bot
* Gmail
* AI Prompt Engineering

---

# 📂 Google Drive Structure

```text
Finance/
│
├── Incoming/
├── Processed/
└── Error/ (Optional)
```

---

# 📊 Google Sheets Structure

| Date | Vendor | Category | Amount | Currency | Payment Method | Tax | Summary |
| ---- | ------ | -------- | ------ | -------- | -------------- | --- | ------- |

---

# 🤖 AI Extraction

The AI extracts and structures the following receipt information:

* Vendor
* Receipt Date
* Total Amount
* Currency
* Expense Category
* Payment Method
* Tax / VAT
* Expense Summary

All extracted values are normalized before being stored in Google Sheets.

---

# 🚨 Large Expense Detection

The workflow automatically checks every expense using an **IF** node.

**Condition**

```text
Amount > ₱5,000
```

If the condition is met, the workflow:

* Sends a Telegram notification
* Sends a Gmail alert
* Moves the receipt to the **Processed** folder

Otherwise, it simply archives the processed receipt.

---

# 📁 Repository Structure

```text
AI-Large-Expense-Tracker-Receipt-Manager/
│
├── workflow.json                 # Exported n8n workflow
├── README.md                     # Project documentation
├── LICENSE
│
├── docs/
│   ├── architecture.png          # Workflow architecture
│   └── workflow.png              # n8n workflow screenshot
│
├── prompts/
│   └── receipt-analysis.md       # AI prompt
│
└── examples/
    └── sample_receipt.pdf        # Sample receipt for testing
```

---

# 📸 Demo

## Workflow

> Add a screenshot of your complete n8n workflow here.

## Google Sheets

> Add a screenshot of the generated expense records.

## Telegram Notification

> Add a screenshot of the large expense alert.

## Gmail Alert

> Add a screenshot of the email notification.

---

# 💡 Use Cases

* Personal expense tracking
* Freelancer bookkeeping
* Small business expense management
* Startup financial automation
* Employee reimbursement
* Receipt digitization
* Expense record keeping

---

# 📚 Learning Outcomes

This project demonstrates experience with:

* AI document processing
* OCR and text extraction
* Prompt engineering
* Structured JSON parsing
* Google Workspace integrations
* JavaScript data normalization
* Conditional workflow routing
* Financial workflow automation
* Production-ready file management

---

# 👨‍💻 Author

**Belio C. Sinangote**

* GitHub: https://github.com/belioautomation

---

⭐ **If you found this project useful, consider giving it a Star!**
