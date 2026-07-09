# certificate-automation-workflow
# 📜 Automated Examination & Certificate Distribution System

![n8n](https://img.shields.io/badge/Automation-n8n-FF6C37?style=flat&logo=n8n) ![JavaScript](https://img.shields.io/badge/Scripting-JavaScript-F7DF1E?style=flat&logo=javascript) ![Status](https://img.shields.io/badge/Project_Status-Production_Ready-success)

## 📌 Project Overview
An enterprise-grade, end-to-end automated workflow built with **n8n** to streamline the process of online examinations, grading, and instant certificate issuance. 

This workflow triggers immediately when a student submits a Google Form, validates their score against a passing threshold, generates a dynamic personalized PDF certificate, and delivers the results via both **Gmail** and **LINE Messaging**.

## 📊 Workflow Logic & Node Architecture
The system is designed with a robust dual-path logic to handle both "Pass" and "Fail" scenarios efficiently, ensuring an optimized User Experience (UX):
<img width="2711" height="1221" alt="Image_25690709_190348_493" src="https://github.com/user-attachments/assets/22323954-d6b7-43dc-a24e-a9585dc77cbf" />


1. **Data Ingestion (Trigger):** Monitors Google Sheets for new exam submissions in real-time.
2. **Conditional Routing (IF Node):** Compares the student's score against the defined `passing_score` threshold.
3. **Dynamic ID & Formatting:** Formats dates and generates a unique Certificate ID template.
4. **Custom Scripting (JavaScript Node):** Executes custom JS to dynamically parse parameters and handle conditional file naming (e.g., saving the file under the student's nickname).
5. **PDF Generation (CloudConvert API):** Transforms a beautifully styled HTML/CSS certificate template into a production-ready PDF asset.
6. **Multi-Channel Notification:** 
   * **On Success:** Emails the PDF certificate via Gmail and broadcasts a congratulatory message with the Certificate ID via LINE.
   * **On Failure:** Sends a supportive, text-based encouragement email and LINE notification encouraging a retake.

## 📂 Repository Contents
* `certificate-automation-workflow.json`: The complete n8n workflow source code (compatible with n8n import feature).
* *(Note: Sensitive credentials, OAuth2 tokens, and API keys have been fully sanitized for security purposes).*

## 🛠️ Tech Stack & Integrations
* **Core Engine:** n8n (Workflow Automation)
* **Programming Language:** JavaScript (Data parsing & payload preparation)
* **Data Layer:** Google Sheets / Google Forms
* **Cloud Infrastructure:** CloudConvert API (HTML-to-PDF compilation)
* **Communication Suite:** Gmail API, LINE Messaging API
