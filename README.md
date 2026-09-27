# Naavik — Voice-First Opportunity Discovery

> An AI-powered voice assistant that helps people discover government job and examination opportunities they may be eligible for — without having to search through dozens of websites and PDFs.

Government opportunities in India are published across multiple portals and often buried inside lengthy notifications. Finding the relevant information is only the first problem; understanding eligibility is another.

**Naavik turns that discovery process into a simple phone conversation.**

---

## The Problem

Government job notifications from organizations such as UPSC, SSC, state PSCs, railways, and banking boards are distributed across different portals.

Applicants often have to:

* Search multiple websites
* Open lengthy PDF notifications
* Extract age, education, category, and deadline requirements
* Manually determine whether they are eligible

This creates a discovery problem, particularly for people who may not be comfortable navigating complex government websites or interpreting lengthy notifications.

---

## What Naavik Does

Naavik combines **AI document processing, eligibility matching, serverless cloud infrastructure, and voice interaction** into one workflow.

### 1. Understand government notifications

Notification PDFs are processed and converted into structured opportunity data.

```text
Government Notification
        │
        ▼
     Amazon S3
        │
        ▼
    AWS Lambda
        │
        ▼
   Amazon Bedrock
        │
        ▼
Structured Opportunity
        │
        ▼
   DynamoDB
```

The extracted information can include:

* Examination / job name
* Eligibility criteria
* Age limits
* Educational requirements
* Category requirements
* Application deadlines
* Official application information

---

### 2. Understand the user

A user enters their phone number through the Naavik interface.

The system then initiates an automated voice interaction and asks for relevant information such as:

* Age
* Education
* Category

---

### 3. Match opportunities

The user's responses are compared against the structured opportunity data.

```text
User Profile
     │
     ▼
Eligibility Matching
     │
     ▼
Relevant Opportunities
     │
     ├──► Voice Response
     │
     └──► SMS / Application Links
```

Instead of searching through notifications manually, the user receives a personalized set of opportunities through the voice interface.

---

## Key Features

### Voice-First Interaction

Users can discover opportunities through a phone conversation rather than navigating multiple portals.

### AI-Powered Document Extraction

Amazon Bedrock is used to extract useful information from unstructured government notification documents.

### Eligibility Matching

Structured opportunity data is matched against information collected from the user.

### Automated Opportunity Database

Extracted opportunities are stored in DynamoDB so they can be queried during user interactions.

### Serverless Architecture

AWS Lambda handles processing and application workflows without requiring a continuously running application server.

---

## System Architecture

Naavik is split into two primary pipelines.

### Notification Processing

```text
Government PDF
      │
      ▼
  Amazon S3
      │
      ▼
  AWS Lambda
      │
      ▼
 Amazon Bedrock
      │
      ▼
Structured Opportunity Data
      │
      ▼
 Amazon DynamoDB
```

### User Interaction

```text
User
 │
 ▼
Naavik Website
 │
 ▼
AWS Lambda
 │
 ▼
Twilio Voice API
 │
 ▼
Voice / IVR Interaction
 │
 ▼
Eligibility Matching
 │
 ▼
DynamoDB
 │
 ├──► Matching Opportunities
 │
 └──► SMS / Official Links
```

---

## Example End-to-End Flow

```text
1. A government notification is uploaded
             ↓
2. The PDF is processed
             ↓
3. AI extracts structured eligibility information
             ↓
4. Opportunity is stored in DynamoDB
             ↓
5. User enters their phone number
             ↓
6. Naavik initiates a voice call
             ↓
7. User provides basic eligibility information
             ↓
8. Relevant opportunities are identified
             ↓
9. Opportunities are communicated through voice
             ↓
10. Official application links can be sent by SMS
```

---

## Technology Stack

| Layer                    | Technologies                    |
| ------------------------ | ------------------------------- |
| AI / Document Processing | Amazon Bedrock, PyPDF2          |
| Cloud                    | AWS Lambda, Amazon S3, DynamoDB |
| Voice                    | Twilio Voice API                |
| Frontend                 | HTML, JavaScript                |
| Data                     | Structured opportunity database |

---

## Why Voice?

The interface is deliberately simple.

Instead of requiring users to:

> search → open PDF → read → interpret eligibility → compare opportunities

Naavik aims to reduce the process to:

> **call → answer → discover**

The voice-first approach is particularly useful for users who may find traditional web-based discovery interfaces difficult to navigate.

---

## Project Context

Naavik was developed as part of a hackathon project exploring how **AI and cloud infrastructure can improve access to public-sector opportunities**.

The project combines:

* Generative AI
* Document understanding
* Eligibility matching
* Serverless architecture
* Voice interfaces
* Public-sector information

The result is a working prototype demonstrating how these technologies can be combined into a single user-facing workflow.

---

## What I Learned

Building Naavik involved working across several layers of an AI application rather than treating the LLM as an isolated component.

The project required connecting:

**unstructured documents → AI extraction → structured data → eligibility logic → cloud workflows → voice interaction**

This made the project an exploration of how an AI system can move beyond generating text and actually participate in an end-to-end application workflow.

---

## Current Status

Naavik is a **prototype / hackathon project**.

The current implementation demonstrates the core workflow from government-notification processing to personalized voice-based opportunity discovery. Further development could expand notification ingestion, eligibility rules, opportunity coverage, and production-scale voice interactions.

---

## Repository Structure

```text
naavik/
│
├── frontend/
├── backend/
├── data/
├── services/
└── README.md
```

> Repository structure may evolve as the project develops.

---

## Vision

Government opportunities already exist.

The problem is often **finding the right opportunity and understanding whether it applies to you**.

Naavik explores a simple idea:

> **Instead of making people search harder, make opportunities easier to discover.**
