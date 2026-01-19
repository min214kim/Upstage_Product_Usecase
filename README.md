# 📘 Upstage Product Usecase
> **Notice:** This repository is a personalized archive and refined version to highlight the specific project I spearheaded within a larger team initiative. While the original repository contains various use cases, I have maintained this version to focus on the Child Counseling Automation System, showcasing my individual technical contributions and problem-solving approach.

> *Original Team Repository: [Upstage_Product_Usecase](https://github.com/UpstageEdu/Upstage_Product_Usecase)*

**Upstage Product Usecase** is a comprehensive collection of demos and hands-on examples that apply Upstage's AI products to real-world domains. 

Designed to be accessible to anyone with a basic understanding of Python and APIs, it provides interactive demo services tailored to professional needs, along with step-by-step implementation guides and source code for hands-on customization.

---

## Featured Project (My Contribution)

### 🌍 NGO/NPO Sector (Collaboration with YBIGTA)

#### Child Counseling Record Analysis & Alert Automation System
- **For detailed codes, please visit this folder > [`NGO_NPO_child_counseling_automation_system/`](./NGO_NPO_child_counseling_automation_system/)**
- **Official implementation guide**: [Upstage Educational Guide](https://edu.upstage.ai/course/ngonpo-usecase-consultation-analysis-alerts)
- **Problem**: Child counseling organizations often struggle with massive amounts of unstructured PDF records, making it difficult to identify high-risk cases promptly.
- **Solution**: Developed an automated pipeline that summarizes counseling logs using Solar LLM, classifies risk levels based on past data, and triggers email notifications to case managers for high-risk situations.

---

## 📄 License
This project is provided for educational and research purposes.

# 📘 Product UseCase Details: Counseling Record Analysis & Alert Automation System

🔗 [Live Demo Link](https://upstage-usecase-ybigta.streamlit.app/)

## 📌 Table of Contents
- [Overview](#-1-overview)
- [Usecase Scenario](#-2-usecase-scenario)
- [Features](#-3-features)
- [Project Structure](#-4-project-structure)
- [Installation & Execution](#-5-installation--execution)
- [How to Use](#-6-how-to-use)
- [Dependencies](#-7-dependencies)
- [API Description](#-8-api-description)
- [Sample Output](#-9-sample-output)
- [Limitations & Notes](#-10-limitations--notes)
- [Contributors](#-11-contributors)
---

## 📜 1. Overview

> This project aims to **optimize counseling record management for non-profit organizations (NPOs)**. By uploading counseling records in PDF format, the system automatically structures the documents and summarizes key points. Furthermore, it analyzes the type of counseling and crisis levels, recommending similar past cases to reduce administrative burden and support rapid response to emergency situations.

### Key Needs Addressed:
1. **Unorganized Records**: Difficulty in searching and analyzing due to fragmented handwritten or PDF documents.
2. **High-Risk Case Detection**: High labor costs for manually identifying critical keywords related to suicide or violence.
3. **Inefficient Case Sharing**: Time-consuming manual search for similar past cases for reference.

### Tech Stack:
![Upstage](https://img.shields.io/badge/Upstage_API-0A0A0A?style=for-the-badge&logo=upstage&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) 
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white) 
![LangChain](https://img.shields.io/badge/LangChain-6442D9?style=for-the-badge&logo=langchain&logoColor=white) 
![FAISS](https://img.shields.io/badge/FAISS-4B83DE?style=for-the-badge&logo=facebook&logoColor=white)

---

## 🎬 2. Usecase Scenario
> When a case manager at a child counseling center uploads a PDF summary of a session, the system provides the following analysis on the dashboard within seconds:

1. **Auto-Summarization**: Summarizes information into client details, key issues, living environment, abuse assessment, emergency level, and overall opinion.
2. **Crisis Classification**: Categorizes the type (e.g., 'Physical Abuse') and determines the severity level.
3. **Similar Case Recommendation**: Suggests the top 3 similar past cases from the AI-Hub counseling database to help establish a response plan.
4. **Emergency Alert**: Automatically sends an email alert to the person in charge if high-risk signs like 'abuse' are detected.

---

## ✨ 3. Features
### Main Features
- **📄 Document Parsing**: Extracts text and structure from PDFs via **Upstage Document AI API**.
- **✨ Text Cleaning**: Anonymizes sensitive personal data (names, schools) to protect privacy.
- **📝 AI Summarization**: Uses **Upstage Solar LLM** to summarize long counseling logs effectively.
- **🏷️ AI Classification**: Automatically classifies 'Counseling Type', 'Crisis Level', and 'Abuse Type'.
- **🔍 Retrieval**: Searches for similar cases within the FAISS vector DB populated with historical datasets.
- **🚨 Alerting**: Sends email notifications to designated managers if the crisis level exceeds a certain threshold.

### Functional Specifications
<details>
<summary><strong>⚙️ View Pipeline Specifications </strong></summary>

- **System Build Pipeline**

| # | Module | Description | Input | Output | Note |
| - | ------------------ | ----------------- | ------- | ----------- | --------------------- |
| 1 | AI-Hub Data Loader | Loads AI-Hub datasets | \*.json | Raw Text | |
| 2 | Text Clean & Anon | Masking names/schools/etc. | Raw Text | Clean Text | |
| 3 | Solar Embedding | Vectorizes counseling content | Clean Text | Vector | Upstage Embedding API |
| 4 | Vector DB Build | Searchable DB construction | Vector + Meta | faiss.index | |

- **User Flow Pipeline**

| # | Module | Description | Input | Output | Note |
| - | ---------------- | ------------------------- | ------ | ------------ | -------------- |
| 1 | PDF Upload | User uploads counseling log | PDF | File Path | |
| 2 | Document Parse | OCR + Structuring | PDF | HTML Text | Upstage API |
| 3 | Text Clean & Anon | Preprocessing & Anonymization | Text | Clean Text | |
| 4 | Solar LLM Summary | Summarizing core content | Clean Text | Summary | |
| 5 | Solar Embedding | Creating embedding vectors | Clean Text | Vector | |
| 6 | Similar Search | Retrieval of 3 cases via FAISS | Vector | Case List | |
| 7 | Solar LLM Classify | Classification of type/level | Clean Text | Results (JSON)| |
| 8 | Risk Alert | Email if Level≥3 or Abuse≠None | Results | Mail Log | |
| 9 | Dashboard | Visualization of results | All | Web Page | Streamlit |

</details>

---

## 📂 4. Project Structure

네, 바로 복사해서 README.md 파일에 붙여넣으실 수 있도록 코드 블록으로 정리해 드립니다.

Markdown

# 📘 Product UseCase: Counseling Record Analysis & Alert Automation System

🔗 [Live Demo Link](https://upstage-usecase-ybigta.streamlit.app/)

## 📌 Table of Contents
- [Overview](#-1-overview)
- [Usecase Scenario](#-2-usecase-scenario)
- [Features](#-3-features)
- [Project Structure](#-4-project-structure)
- [Installation & Execution](#-5-installation--execution)
- [How to Use](#-6-how-to-use)
- [Dependencies](#-7-dependencies)
- [API Description](#-8-api-description)
- [Sample Output](#-9-sample-output)
- [Limitations & Notes](#-10-limitations--notes)
- [Contributors](#-11-contributors)

---

## 📜 1. Overview

> This project aims to **optimize counseling record management for non-profit organizations (NPOs)**. By uploading counseling records in PDF format, the system automatically structures the documents and summarizes key points. Furthermore, it analyzes the type of counseling and crisis levels, recommending similar past cases to reduce administrative burden and support rapid response to emergency situations.

### Key Needs Addressed:
1. **Unorganized Records**: Difficulty in searching and analyzing due to fragmented handwritten or PDF documents.
2. **High-Risk Case Detection**: High labor costs for manually identifying critical keywords related to suicide or violence.
3. **Inefficient Case Sharing**: Time-consuming manual search for similar past cases for reference.

### Tech Stack:
![Upstage](https://img.shields.io/badge/Upstage_API-0A0A0A?style=for-the-badge&logo=upstage&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white) 
![Streamlit](https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white) 
![LangChain](https://img.shields.io/badge/LangChain-6442D9?style=for-the-badge&logo=langchain&logoColor=white) 
![FAISS](https://img.shields.io/badge/FAISS-4B83DE?style=for-the-badge&logo=facebook&logoColor=white)

---

## 🎬 2. Usecase Scenario
> When a case manager at a child counseling center uploads a PDF summary of a session, the system provides the following analysis on the dashboard within seconds:

1. **Auto-Summarization**: Summarizes information into client details, key issues, living environment, abuse assessment, emergency level, and overall opinion.
2. **Crisis Classification**: Categorizes the type (e.g., 'Physical Abuse') and determines the severity level.
3. **Similar Case Recommendation**: Suggests the top 3 similar past cases from the AI-Hub counseling database to help establish a response plan.
4. **Emergency Alert**: Automatically sends an email alert to the person in charge if high-risk signs like 'abuse' are detected.

---

## ✨ 3. Features
### Main Features
- **📄 Document Parsing**: Extracts text and structure from PDFs via **Upstage Document AI API**.
- **✨ Text Cleaning**: Anonymizes sensitive personal data (names, schools) to protect privacy.
- **📝 AI Summarization**: Uses **Upstage Solar LLM** to summarize long counseling logs effectively.
- **🏷️ AI Classification**: Automatically classifies 'Counseling Type', 'Crisis Level', and 'Abuse Type'.
- **🔍 Retrieval**: Searches for similar cases within the FAISS vector DB populated with historical datasets.
- **🚨 Alerting**: Sends email notifications to designated managers if the crisis level exceeds a certain threshold.

### Functional Specifications
<details>
<summary><strong>⚙️ View Pipeline Specifications </strong></summary>

- **System Build Pipeline**

| # | Module | Description | Input | Output | Note |
| - | ------------------ | ----------------- | ------- | ----------- | --------------------- |
| 1 | AI-Hub Data Loader | Loads AI-Hub datasets | \*.json | Raw Text | |
| 2 | Text Clean & Anon | Masking names/schools/etc. | Raw Text | Clean Text | |
| 3 | Solar Embedding | Vectorizes counseling content | Clean Text | Vector | Upstage Embedding API |
| 4 | Vector DB Build | Searchable DB construction | Vector + Meta | faiss.index | |

- **User Flow Pipeline**

| # | Module | Description | Input | Output | Note |
| - | ---------------- | ------------------------- | ------ | ------------ | -------------- |
| 1 | PDF Upload | User uploads counseling log | PDF | File Path | |
| 2 | Document Parse | OCR + Structuring | PDF | HTML Text | Upstage API |
| 3 | Text Clean & Anon | Preprocessing & Anonymization | Text | Clean Text | |
| 4 | Solar LLM Summary | Summarizing core content | Clean Text | Summary | |
| 5 | Solar Embedding | Creating embedding vectors | Clean Text | Vector | |
| 6 | Similar Search | Retrieval of 3 cases via FAISS | Vector | Case List | |
| 7 | Solar LLM Classify | Classification of type/level | Clean Text | Results (JSON)| |
| 8 | Risk Alert | Email if Level≥3 or Abuse≠None | Results | Mail Log | |
| 9 | Dashboard | Visualization of results | All | Web Page | Streamlit |

</details>

---

## 📂 4. Project Structure
The source code structure of this project is as follows, provided for development and maintenance reference. End users interact with the service exclusively through the web application UI.

```
├── document_example/      # PDF samples for demo
│   └── ... 
├── faiss_index/
│   ├── index.faiss        # FAISS vector DB index files 
│   └── index.pkl          # Serialized files related to FAISS index
├── images/                # Image data directory
│   └── ... 
├── origin/                # Original data directory
│   └── ... 
├── processed/
│   └── ...                # Preprocessed data directory
├── utils/
│   ├── classifier.py      # Classification via Solar LLM
│   ├── document_parser.py # Document parsing module (OCR) 
│   ├── embedder.py        # Text embedding module
│   ├── logger.py          # Logging configuration module
│   ├── mailer.py          # Email notification module
│   ├── renderer.py        # UI rendering utility module
│   ├── search_faiss.py    # FAISS index search module
│   ├── sidebar.py         # Streamlit sidebar module
│   ├── summarizer.py      # Counseling summary module via Solar LLM
│   └── text_cleaner.py    # Text cleaning & anonymization module
├── .env.example           # Example environment variables file
├── .gitignore             # List of files excluded from Git tracking
├── app.py                 # Main Streamlit web application execution file
├── data_processing.py     # Script for data preprocessing & FAISS DB build
├── embedding.py           # Script for embedding generation
├── readme.md              # Project documentation 
├── requirements.txt       # Project dependency package list
├── run_demo.sh            # Demo execution script
├── runtime.txt            # Python version specification (for deployment)
└── test.py                # Test code 
```

---

## 🚀 5. Installation & Execution

**1. Access the Service**
- Access the URL provided below through your web browser.
- 🔗 [URL](https://upstage-usecase-ybigta.streamlit.app/)

**2. For Admins: Environment Variable Setup**
- This service manages sensitive information, such as Upstage API keys and email server details, through the deployment environment's Environment Variables or Secrets management features.
- The `.env` file used in local development is not used in the server deployment environment. Admins must securely input API keys directly in the settings menu of the deployment platform (e.g., Streamlit Community Cloud, AWS, Google Cloud).

---
## 📖 6. How to Use

🔗 [Direct Link to Project](https://upstage-usecase-ybigta.streamlit.app/)

### PDF Upload
![Upload PDF](./images/pdf업로드.gif)
- After accessing the service URL, drag and drop the counseling record PDF file to be analyzed into the file upload window at the bottom of the screen, or select it manually.
- Once the upload is complete, the progress from parsing, preprocessing, summarization, similar case search, to classification will be displayed.

### Check Results
- Once processing is complete, the following analysis results will appear on the dashboard.

**1. Current Session Summary**
- A summary of the client's profile, key issues, living environment, abuse status, emergency level, and comprehensive assessment is displayed.
- Click "View Original Text" to check the full text.
![Session Summary](./images/결과1.gif)

**2. View Past Similar Cases**
- Detailed information on 3 similar cases based on AI-Hub data can be reviewed.
- Click the "View Counseling Content/Information by Question" toggle to see the full content of the similar cases.
![Past Similar Cases](./images/결과2.gif)

**3. View Risk Analysis & Send Email Notification**
- You can check the severity level and abuse type categorized for the session.
- If determined as high-risk, a risk notification email can be sent to the person in charge.
- For guidance on sending emails, please refer to the sidebar on the left side of the screen.
![Risk Analysis & Email Sender](./images/결과3.gif)

---
## 📦 7. Dependencies
This project uses the libraries specified in `requirements.txt`.
```
streamlit>=1.32.0
python-dotenv>=1.0.0
numpy>=1.24.0

LangChain and Upstage
langchain>=0.1.17
langchain-core>=0.1.50
langchain-community>=0.0.25
langchain-upstage>=0.0.20

Vector DB
faiss-cpu>=1.7.4

Email support
secure-smtplib
```

---
## 🔌 8. API Description
-   **Upstage Document AI API**: Used for analyzing PDF layouts and extracting text (OCR).
-   **Upstage Solar LLM API**: Used for summarizing content based on the extracted text and classifying counseling types, crisis levels, and abuse types.
-   **Upstage Embedding API**: Converts cleaned text into high-dimensional vectors to enable similarity-based searches.

---

## 🎯 9. Sample Output (Screenshots)

<details>
<summary><strong>Click to view sample output screenshots</strong></summary>

**1. Current Session Summary** 
![Session Summary 1](./images/결과1-1.png)
![Session Summary 2](./images/결과1-2.png)
![Session Summary 3](./images/결과1-3.png)


**2. Past Similar Cases** 
![Similar Cases 1](./images/결과2-1.png)
![Similar Cases 2](./images/결과2-2.png)

**3. Risk Analysis & Email Notification** 
![Risk Analysis Result](./images/결과3.png)
</details>

## ⚠️ 10. Limitations & Notes
- **API Key Management**: Upstage API keys configured in the deployment environment (e.g., Streamlit Community Cloud, AWS Secrets Manager) must be managed securely to prevent exposure. Do not include API keys directly in the source code or public repositories.
- **Data Dependency**: The accuracy of the similar case recommendation feature depends on the AI-Hub counseling data built into the `faiss_index`.
- **Document Format**: The system is currently optimized for text-based PDF counseling records; performance may decrease for documents containing complex tables or images.
  
---

## 🧑‍🤝‍🧑 11. Contributors / License
### Contributors
Heechan Yoon, Minseo Kim, Chanwoo Moon, Junhyun Bang, Hwirin Song
  
<a href="https://github.com/quant-jason">
  <img src="https://github.com/quant-jason.png" width="50px" alt="윤희찬"/>
</a>
<a href="https://github.com/min214kim">
  <img src="https://github.com/min214kim.png" width="50px" alt="김민서"/>
</a>
<a href="https://github.com/urbanking">
  <img src="https://github.com/urbanking.png" width="50px" alt="문찬우"/>
</a>
<a href="https://github.com/bindingflare">
  <img src="https://github.com/bindingflare.png" width="50px" alt="방준현"/>
</a>
<a href="https://github.com/Hwiplash">
  <img src="https://github.com/Hwiplash.png" width="50px" alt="송휘린"/>
</a>
