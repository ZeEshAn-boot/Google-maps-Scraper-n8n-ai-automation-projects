# AI-Powered Business Lead Scraping & Qualification Automation

An AI-powered **n8n automation workflow** designed to scrape business data, enrich lead information, extract contact details, validate email addresses, analyze business data using AI, and prepare qualified leads for sales outreach and automation.

---

## 📌 Project Overview

This project automates the process of discovering and qualifying business leads.

The workflow can:

* Scrape business information
* Extract business contact details
* Identify owner or doctor names
* Extract social media profiles
* Extract appointment methods
* Analyze Google ratings
* Assign lead priority
* Assign lead status
* Identify the business city
* Validate email addresses
* Check phone numbers
* Track call status
* Track automation status
* Add notes for each lead

The workflow is designed to reduce manual lead research and organize business data into a structured format for further sales and outreach automation.

---

## ⚙️ Workflow Architecture

```text
Business Search Input
        │
        ▼
AI Agent
        │
        ▼
Scrape Data Tool
        │
        ▼
Business Data Collection
        │
        ▼
Website & Social Media Analysis
        │
        ▼
AI Data Extraction
        │
        ▼
Email Validation
        │
        ▼
Phone Validation
        │
        ▼
Lead Qualification
        │
        ▼
Data Structuring
        │
        ▼
Qualified Lead Output
```

---

## 🤖 AI-Powered Data Extraction

The workflow uses an AI model to analyze business information and extract structured data.

The AI extracts the following information:

```json
{
  "email": "",
  "owner_or_doctor_name": "",
  "social_media_links": "",
  "appointment_method": "",
  "google_rating": "",
  "lead_priority": "",
  "lead_status": "",
  "follow_up_details": "",
  "call_status": "",
  "automation_status": "",
  "notes": ""
}
```

The extracted data is then combined with the original scraped business information.

---

## 📊 Business Data Collected

The workflow can structure business information such as:

| Field                  | Description                   |
| ---------------------- | ----------------------------- |
| `id`                   | Unique business identifier    |
| `name`                 | Business name                 |
| `phone_number`         | Business phone number         |
| `address`              | Business address              |
| `city`                 | Business city                 |
| `zone`                 | Business zone                 |
| `country_code`         | Country code                  |
| `url`                  | Business listing URL          |
| `rating`               | Business rating               |
| `status`               | Business status               |
| `opening_status`       | Opening status                |
| `website`              | Official website              |
| `email`                | Extracted email               |
| `owner_or_doctor_name` | Owner or doctor name          |
| `facebook`             | Facebook profile URL          |
| `instagram`            | Instagram profile URL         |
| `twitter`              | Twitter/X profile URL         |
| `appointment_method`   | Booking or appointment method |
| `lead_priority`        | Lead priority                 |
| `lead_status`          | Lead qualification status     |
| `call_status`          | Calling progress              |
| `automation_status`    | Automation progress           |
| `notes`                | Additional lead notes         |

---

## 🔍 Lead Qualification

The workflow analyzes the collected information and helps categorize leads based on their quality and potential.

### Lead Priority

Possible examples:

```text
High
Medium
Low
```

### Lead Status

Possible examples:

```text
New
Qualified
Contacted
Interested
Not Interested
Converted
```

### Call Status

Possible examples:

```text
Pending
Called
Answered
No Answer
Follow Up
Completed
```

### Automation Status

Possible examples:

```text
Not Started
In Progress
Completed
Failed
```

These statuses can be used to track the complete lead outreach process.

---

## 📧 Email Validation

The workflow includes email validation to determine whether an email address is suitable for outreach.

### `valid`

The email address is confirmed as valid and the mailbox can receive emails.

### `accept_all`

The mail server accepts emails for all addresses on the domain. The exact mailbox cannot be completely verified.

### `invalid`

The email address or domain is invalid, unavailable, or does not have the required mail server records.

> Invalid emails should generally be excluded from email outreach campaigns.

---

## 📞 Phone Number Validation

The workflow can also process and validate business phone numbers.

This helps determine whether the phone number is suitable for calling and outreach activities.

---

## 🌐 Social Media Extraction

The workflow extracts social media information and separates it into individual fields.

Example:

```text
Facebook  → facebook
Instagram → instagram
Twitter/X → twitter
```

This makes the data easier to use in:

* CRM systems
* Lead dashboards
* Sales automation
* Social media outreach
* Marketing campaigns

---

## 🏙️ City Extraction

The workflow extracts the city from the business address or AI-generated data.

Example:

```text
Address:
Dubai, United Arab Emirates

City:
Dubai
```

The city is then stored as a separate field for easier filtering and lead segmentation.

---

## 🧠 AI Agent & Sub-Workflow

The workflow uses an AI Agent to interact with the scraping workflow.

The AI Agent can provide parameters such as:

```json
{
  "country": "United Arab Emirates",
  "city": "Dubai",
  "clinic_type": "Skin Clinic"
}
```

These parameters are passed to the scraping sub-workflow to collect relevant business leads.

---

## 🛠️ Technologies Used

* **n8n** – Workflow automation
* **AI Agent** – Intelligent workflow control
* **Groq API** – AI-powered data extraction
* **Llama 3.3 70B** – Large language model
* **Google Maps / Business Data** – Business lead discovery
* **Email Validation API** – Email verification
* **Phone Validation API** – Phone verification
* **JavaScript** – Data processing and transformation
* **JSON** – Structured data exchange

---

## 🔄 Data Processing Flow

```text
1. Receive business search requirements
2. AI Agent processes the request
3. Scrape business data
4. Collect business details
5. Check website availability
6. Extract emails and contact information
7. Extract owner or doctor name
8. Extract social media profiles
9. Extract appointment methods
10. Analyze business rating
11. Validate email address
12. Validate phone number
13. Assign lead priority
14. Assign lead status
15. Add call and automation status
16. Generate notes
17. Structure the final lead data
```

---

## 📁 Example Final Output

```json
{
  "id": "business-id",
  "name": "Example Skin Clinic",
  "phone_number": "+971XXXXXXXXX",
  "address": "Dubai, UAE",
  "city": "Dubai",
  "country_code": "AE",
  "website": "https://example.com",
  "rating": 4.8,
  "email": "info@example.com",
  "owner_or_doctor_name": "Dr. Example",
  "facebook": "https://facebook.com/example",
  "instagram": "https://instagram.com/example",
  "twitter": "",
  "appointment_method": "Website Booking",
  "google_rating": "4.8",
  "lead_priority": "High",
  "lead_status": "Qualified",
  "call_status": "Pending",
  "automation_status": "Not Started",
  "follow_up_details": "Contact the business for AI automation services.",
  "notes": "Business has an active website and social media presence."
}
```

---

## 🚀 Setup & Installation

### 1. Import the Workflow

Download the workflow JSON file and import it into your n8n instance.

You can use:

* n8n Cloud
* Self-hosted n8n
* Local n8n installation

---

### 2. Configure API Credentials

Add the required credentials inside n8n.

Required credentials may include:

* Groq API Key
* Business data or scraping API credentials
* Email validation API credentials
* Phone validation API credentials

> Never upload API keys, access tokens, passwords, or private credentials to GitHub.

---

### 3. Configure the AI Model

The workflow uses the Groq API with the Llama 3.3 70B model for structured data extraction.

The AI is instructed to return structured JSON data with predefined fields.

---

### 4. Configure the Scraping Sub-Workflow

Make sure the scraping sub-workflow is correctly connected to the main workflow through the appropriate **Execute Workflow** or AI Agent Tool node.

The scraping workflow should correctly receive the required parameters:

```text
Country
City
Business Type
```

---

### 5. Test the Workflow

Run the workflow using a single test input.

Verify that:

* Business information is collected
* Website data is processed
* Emails are extracted
* Emails are validated
* Phone numbers are processed
* Social media profiles are extracted
* Lead status is assigned
* All final fields are correctly structured

---

## 🔐 Security

Never commit sensitive information to GitHub.

Do not upload:

```text
API Keys
Access Tokens
Passwords
Private Credentials
Database Passwords
Webhook Secrets
```

Use n8n Credentials or environment variables to securely store sensitive information.

---

## 📈 Future Improvements

Possible future improvements include:

* CRM integration
* Automated email outreach
* Automated phone calling
* WhatsApp integration
* Instagram DM automation
* Lead scoring system
* Automatic follow-up scheduling
* Google Sheets integration
* MongoDB integration
* PostgreSQL integration
* Sales dashboard
* AI-generated outreach messages
* Automated lead status updates

---

## 🎯 Project Goal

The main goal of this project is to automate the complete business lead generation and qualification process.

Instead of manually:

```text
Searching Businesses
        ↓
Collecting Data
        ↓
Finding Emails
        ↓
Checking Phone Numbers
        ↓
Finding Social Media
        ↓
Qualifying Leads
```

The entire process is automated using **n8n, AI, APIs, and JavaScript data processing**.

---

## 👨‍💻 Author

**Muhammad Zeeshan**

Computer Science Student | AI Automation Developer | n8n Workflow Developer

---

## ⭐ Project Highlights

* AI-powered lead generation
* Automated business data scraping
* Structured JSON data extraction
* Email validation
* Phone number validation
* Social media extraction
* AI-based lead qualification
* Call tracking
* Automation tracking
* Follow-up management
* Scalable n8n architecture
