
# 🤖 Automated Billing & Payment Reminder Chatbot (n8n Workflow)

## 📌 Overview

This project implements an **end-to-end automated billing assistant** using **n8n** that interacts with users via **Telegram** to collect bill details, process invoices, store structured data, and send **payment reminders and confirmations**.
The workflow supports both **text-based bill inputs** and **uploaded invoice documents**, enabling a flexible and intelligent billing experience.

The system integrates **OCR, LLM-based invoice parsing, Google Sheets for record management, and Telegram-based conversational interaction**, making it suitable for small businesses and automated finance workflows.

---

## 🎯 Key Objectives

* Collect invoice and bill details through a chatbot interface
* Automatically extract structured invoice data from uploaded documents
* Store and manage billing records centrally
* Ask users for payment confirmation and status
* Send reminders and notifications for pending or completed payments
* Reduce manual intervention in billing follow-ups

---

## 🧩 Workflow Architecture

### 1. **User Interaction (Telegram Bot)**

* Users interact with the chatbot via Telegram
* Supports:

  * Text-based bill details
  * Invoice/document uploads
  * Confirmation responses (Yes / No / Payment Status)

---

### 2. **Invoice Upload & OCR Processing**

* Uploaded invoices are sent to **LlamaIndex Parse API**
* OCR converts invoices into structured markdown text
* Workflow waits for processing completion before proceeding

---

### 3. **LLM-Based Invoice Data Extraction**

* Extracts key invoice fields using an LLM:

  * Invoice Number
  * Invoice Date
  * Due Date
  * Seller & Buyer Details
  * Line Items
  * Subtotal, Tax, Total Amount
  * Payment Terms and Bank Details
* Outputs a clean, validated **JSON structure**
* Missing values are handled safely as `null`

---

### 4. **Data Storage (Google Sheets)**

* Parsed invoice data is appended to a Google Sheet
* Acts as a lightweight billing database
* Supports:

  * Insert
  * Update (payment status)
  * Delete (invoice removal)
  * Sorting and limiting recent invoices

---

### 5. **Payment Confirmation & Reminder Logic**

* Bot asks users to verify extracted invoice details
* Requests payment status from the user
* Updates payment status in Google Sheets
* Sends confirmation or reminder messages via Telegram

---

## 🛠️ Technologies Used

* **n8n** – Workflow automation
* **Telegram Bot API** – User interaction
* **LlamaIndex Parse API** – OCR & document parsing
* **Google Gemini (LLM)** – Intelligent invoice data extraction
* **Google Sheets API** – Billing data storage
* **Google Drive API** – Temporary file handling
* **JavaScript (n8n Code Nodes)** – JSON parsing & logic

---

## 🚀 How to Use

1. Import the workflow JSON into n8n
2. Configure credentials:

   * Telegram Bot
   * Google Sheets
   * Google Drive
   * LlamaIndex API
   * Google Gemini API
3. Activate the workflow
4. Start chatting with the Telegram bot:

   * Upload invoices
   * Confirm extracted data
   * Update payment status
5. Monitor billing records in Google Sheets

---

## ✅ Features Summary

* ✔ Multi-input support (text + documents)
* ✔ Automated OCR and structured data extraction
* ✔ Intelligent validation using LLMs
* ✔ Centralized billing database
* ✔ Payment reminders and confirmations
* ✔ Minimal manual intervention

---

## ⚠️ Disclaimer

This workflow is intended for **automation and productivity purposes** only.
It does not replace professional accounting or financial systems and should be used with appropriate validation in production environments.

---

## 👤 Author

**Charvi Ningala**

---

