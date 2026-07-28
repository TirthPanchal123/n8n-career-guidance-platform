# AI-Powered Career Guidance & Student Success Platform 🚀

> **n8n Summer School '26 Capstone Project Final Submission**  
> **Domain**: Education & Career Development | **Assignment**: 14

![n8n Workflows](https://img.shields.io/badge/n8n-Workflow%20Automation-FF6D5A?style=for-the-badge&logo=n8n)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--3.5/4-412991?style=for-the-badge&logo=openai)
![Google Sheets](https://img.shields.io/badge/Google%20Sheets-Database-34A853?style=for-the-badge&logo=googlesheets)
![JavaScript](https://img.shields.io/badge/Frontend-HTML5%2FCSS3%2FJS-F7DF1E?style=for-the-badge&logo=javascript)

---

# 🌐 Live Demo

**Frontend (Netlify)**

👉 https://tangerine-lolly-278d55.netlify.app/

Students can directly access the AI Career Assessment Portal, complete the assessment form, and trigger the automated n8n workflow.

---
## 📌 Executive Summary
The **AI-Powered Career Guidance & Student Success Platform** is an enterprise-grade modular automation system built using **n8n**, **OpenAI**, **Google Sheets**, and a custom **Web Frontend**. It solves the scaling challenge faced by university career guidance centers by converting student assessment submissions into instant AI skill-gap evaluations, personalized 4-week roadmaps, matched learning resources, active internship opportunities, and automated weekly progress check-ins.

---

## 🏗️ Architecture Overview

The platform consists of **5 interconnected sub-workflows** comprising **26 total nodes**:

```
[ Web UI / n8n Form ] 
       │
       ▼
[ WF-01: Data Processor ] ➔ [ Google Sheets DB ]
       │
       ▼
[ WF-02: AI Engine ] ➔ [ OpenAI GPT Analysis ]
       │
       ▼
[ WF-03: Resource Matcher ] ➔ [ Courses & Internship DB ]
       │
       ▼
[ WF-04: Report Dispatcher ] ➔ [ Student Gmail Inbox ]
       
[ WF-05: Weekly Cron ] ➔ [ Cohort Engagement Audit ] (Runs Weekly)
```

---

## 📁 Repository Structure

```
├── frontend/
│   └── index.html                
├── workflows/
│   ├── 01_student_registration_data_processor.json
│   ├── 02_ai_career_recommendation_engine.json
│   ├── 03_automated_course_internship_matcher.json
│   ├── 04_multichannel_report_dispatcher.json
│   └── 05_scheduled_weekly_progress_tracker.json
└── documentation/
    ├── problem_analysis_and_architecture.md
    ├──AI-Powered-Career-Guidance-Platform.pptx
```

---

## 🚀 Quick Setup & Import Guide

### Prerequisites
1. **n8n Instance**: Running locally (`n8n start`) or hosted on n8n Cloud.
2. **OpenAI API Key**: For AI recommendation nodes.
3. **Google Account**: For Google Sheets DB & Gmail sending nodes.

### Step 1: Import Workflows into n8n
1. Open your n8n canvas (`http://localhost:5678`).
2. Click **Workflows** ➔ **Import from File**.
3. Import all 5 JSON files from the `workflows/` directory.

### Step 2: Set Credentials
- **OpenAI Node**: Add your OpenAI API key in `WF-02` & `WF-05`.
- **Gmail Node**: Connect your Google Account OAuth2 or App Password in `WF-04`.
- **Google Sheets Node**: Connect Google Sheets OAuth2 and set your Spreadsheet ID in `WF-01`, `WF-04`, and `WF-05`.

### Step 3: Activate Workflows & Launch Frontend
1. Turn the **Active** toggle to `ON` for all 5 workflows.
2. Open `frontend/index.html` in your browser (Double click file).
3. Ensure the Webhook URL matches `http://localhost:5678/webhook/student-career-registration`.
4. Fill out the form and submit!

---

## 📊 Verification & Features Checklist

| Requirement | Built Status | Implementation Detail |
|---|---|---|
| Workflows Count | **5 Workflows** | Modular sub-workflow chain via HTTP Webhooks |
| Total Node Count | **26 Nodes** | Complete logic coverage from input to dispatch |
| AI Integration | **OpenAI GPT** | Dynamic skill gap analysis & personalized 4-week roadmap |
| Database Storage | **Google Sheets** | Real-time record insertion and status updates |
| User Interface | **Web Form & n8n Form** | Dual input interface (Custom Web UI + n8n Form Trigger) |
| Output Delivery | **HTML Email Dispatch** | Rich styled HTML roadmap delivered via Gmail |
| Cron Schedule | **Weekly Automation** | Automated Sunday 9 AM progress audit and tip email |

---

## 🎓 Author & Credits
Built for **Summer School '26 N8N Capstone Final Project**.
