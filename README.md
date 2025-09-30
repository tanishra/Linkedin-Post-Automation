# 🤖 LinkedIn Post Automation with n8n

This project automates the process of posting to **LinkedIn** using [n8n](https://n8n.io/), while also tracking posts in **Google Sheets**, generating CSV reports, uploading them to **Google Drive**, and sending email notifications on success or failure.

---

## 📌 What This Project Does

This automation reads post descriptions from a Google Sheet and goes through the following steps:

1. 🔄 **Reads unposted content** from Google Sheets.
2. 🤖 **Uses Gemini-2.5-flash model** to generate detailed LinkedIn post content based on the short description.
3. 📤 **Posts the content to LinkedIn** via LinkedIn API.
4. ✅ **Updates the post status** in Google Sheets as "Posted".
5. 📧 **Sends a success or failure email** notification after each attempt.
6. 📄 **Generates a structured `.csv` report** containing the post description, URN, and timestamp.
7. ☁️ **Uploads that report to Google Drive** as a binary file.

> This is ideal for marketing teams, personal brand builders, or agencies who want to semi-automate their content distribution via LinkedIn.

---

## ✨ Features

- Read & filter posts from Google Sheets
- AI content generation based on short description
- LinkedIn post publishing
- Real-time post status updates
- Success & failure email alerts
- Structured `.csv` reporting
- Google Drive integration for report storage
- Error handling with conditional logic
- Fully modular & reusable workflow

---

## 📸 Workflow Overview

![LinkedIn Automation Workflow](./assets/n8n_workflow.png)

---

## ⚙️ Requirements

Before running this workflow, ensure you have the following:

### 🔐 Credentials Needed
- **Google Sheets** (OAuth2 or service account)
- **Google Drive** access
- **LinkedIn Developer Account**
  - With access token and proper API permissions
- **Email SMTP** credentials
- (Optional) **OpenAI / Claude / Gemini API Key** for AI content generation

---

## 🚀 How to Use This Project

🧩 Step 1: Clone the Repository
```bash
git clone https://github.com/tanishra/Linkedin-Post_Automation.git
cd n8n-linkedin-automation
```

🧩 Step 2: Import the Workflow into n8n
- Open your n8n instance
- Click Import using file
- Upload workflow/Linkedin_Post_Automation.json

🧩 Step 3: Configure Credentials
- Set up these credentials in n8n:
- Google Sheets
- Google Drive
- LinkedIn API
- Email (SMTP or OAuth2)
- AI Provider (if applicable)

🧩 Step 4: Customize Google Sheet
- Prepare your sheet with at least these columns:
Post Description	URLs        Post Status

🧩 Step 5: Run the Workflow
You can:
- Run it manually from the editor
- Or set it on a schedule trigger to run daily

--- 

## ❌ Error Handling
- If a post fails (e.g. invalid token, network error), the workflow:
1. Sends a failure email to your address
2. Does not update the post status in the sheet
- If successful:
1. Updates post status and uploads report

---

## 🙌 Contributing
Contributions are welcome! Here's how:
- Fork the repo
- Create a feature branch
- Make your changes
- Submit a PR with a clear description
	
