# Naavik – Voice-First Opportunity Discovery System

Naavik is an AI-powered voice assistant that helps users discover government job and exam opportunities they are eligible for through a simple automated phone call.

Government job notifications in India are scattered across hundreds of websites and are typically published as lengthy PDF documents. For many users—especially first-time applicants and those in rural areas—simply discovering relevant opportunities becomes difficult.

Naavik solves this problem by automatically extracting information from government notifications and delivering personalized opportunity suggestions through a voice interface.

---

## Problem

Millions of government job aspirants rely on official notifications released by various agencies such as UPSC, SSC, state PSCs, railways, and banking boards. However:

- Notifications are spread across multiple portals
- Most announcements are published as **complex PDF documents**
- Eligibility requirements are difficult to interpret
- Users must manually search multiple websites

As a result, many candidates miss opportunities they are actually eligible for.

---

## Solution

Naavik provides a **voice-first discovery platform** where users can learn about opportunities through a simple phone call.

Instead of manually searching multiple websites, users can:

1. Enter their phone number on the Naavik website
2. Receive an automated voice call
3. Answer simple questions such as:
   - Age
   - Education
   - Category
4. Instantly hear opportunities they are eligible for

After the call, the system can also send **SMS links to the official application pages**, making it easier to apply.

---

## Key Features

- Voice-based opportunity discovery
- AI-powered extraction of information from government notifications
- Eligibility matching based on user profile
- Automated database of government opportunities
- Serverless architecture for scalable processing

---

## Technologies Used

**Cloud Infrastructure**
- AWS Lambda
- Amazon S3
- Amazon DynamoDB

**AI & Document Processing**
- Amazon Bedrock
- PyPDF2

**Voice Communication**
- Twilio Voice API

**Frontend**
- HTML
- JavaScript

---

## System Architecture

### Notification Processing Pipeline

Government Notification PDF  
→ Amazon S3  
→ AWS Lambda Processing  
→ Amazon Bedrock (Information Extraction)  
→ DynamoDB Opportunity Database

### User Interaction Pipeline

User  
→ Website  
→ AWS Lambda  
→ Twilio Voice Call  
→ IVR Interaction  
→ Eligibility Engine  
→ DynamoDB

---

## Example User Flow

1. A government job notification PDF is uploaded to the system.
2. The system extracts key details such as eligibility criteria, age limits, education requirements, and deadlines.
3. The extracted information is stored in a structured opportunity database.
4. A user enters their phone number on the website.
5. The system places an automated voice call and asks eligibility questions.
6. Based on the responses, Naavik identifies opportunities the user qualifies for.
7. Relevant opportunities are communicated to the user during the call.

---

## Impact

Naavik aims to make government opportunities **more accessible and easier to discover** by:

- Reducing the need to manually search multiple websites
- Simplifying complex government notifications
- Making opportunity discovery accessible through voice interaction

The goal is to ensure that **opportunities reach the people who are eligible for them**.


## Project Context

Naavik was developed as part of a hackathon project exploring how AI and cloud infrastructure can improve access to public sector opportunities.
