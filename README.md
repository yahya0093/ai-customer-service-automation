# 🤖 AI Customer Service Automation

An end-to-end AI-powered customer service system built with **n8n**, integrating **Freshchat, Freshdesk, OpenAI, Supabase, APIs, and workflow state management**.

The system is designed to handle the complete customer support lifecycle — from the first customer message, through issue collection and ticket creation, to department resolution and final customer follow-up.

---

## 🚀 Project Overview

This project goes beyond a standard chatbot.

It combines AI reasoning, workflow automation, customer data, ticket management, conversation state, and human-agent collaboration into a complete customer service architecture.

The system can understand customer requests, collect missing information, manage active issues, create support tickets, pause automation when a human agent takes over, and continue the customer journey after the responsible team provides a resolution.

---

## ✨ Key Features

* 🤖 AI-powered customer conversations and intent handling
* 💬 Freshchat & WhatsApp conversation integration
* 🎫 Automatic Freshdesk ticket creation
* 🧠 Complaint and request classification
* 🔍 Customer and order data lookup through APIs
* 🗂️ Stateful issue management across multiple messages
* 🛡️ Duplicate issue and duplicate ticket prevention
* 🖼️ Multi-image buffering and evidence handling
* 🔄 Human-agent handoff with AI pause/resume logic
* 📌 Active issue lifecycle tracking
* 🧩 Supabase-based message and image buffering
* 📋 Persistent issue tracking and operational state updates
* 🔁 Automated department-resolution follow-up
* 🧠 AI classification of internal resolutions
* ✅ Separate handling for normal and final resolutions
* ⏱️ WhatsApp 24-hour messaging-window validation
* 📧 Automatic fallback notification when direct WhatsApp delivery is unavailable

---

## 🏗️ System Architecture

```text
Customer
   ↓
Freshchat / WhatsApp
   ↓
n8n Event Processing
   ↓
Customer Context + Conversation State
   ↓
AI Customer Service Agent
   ↓
┌──────────────────────────────┐
│ Customer & Order APIs        │
│ Supabase                     │
│ Issue State Management       │
│ Image / Message Buffers      │
└──────────────────────────────┘
   ↓
Freshdesk Ticket Creation
   ↓
Responsible Team
   ↓
Freshdesk Resolution Webhook
   ↓
AI Resolution Classification
   ↓
Customer-Facing Resolution
   ↓
Freshchat / WhatsApp
```

---

## 🔄 Customer Issue Lifecycle

The system maintains an active issue state instead of treating every customer message as an isolated interaction.

```text
Collecting
   ↓
Pending
   ↓
Awaiting Customer Reply
   ↓
Operational Follow-Up
   ↓
Resolved / Closed
```

This allows the AI to preserve context across messages and prevents duplicate support tickets while an existing issue is still being handled.

---

## 🧠 Resolution Intelligence

A separate workflow processes updates coming back from Freshdesk.

The AI determines whether the update represents:

* 💬 A new customer-facing resolution
* ⚙️ An internal operational update
* ✅ A final customer-facing decision

Customer-facing resolutions are rewritten into clear, natural messages before being sent back to the customer.

The workflow also checks the WhatsApp communication window before sending a response and triggers a manual follow-up path when direct messaging is no longer available.

---

## 👨‍💼 Human + AI Collaboration

The system is designed to work alongside human support agents.

When a human agent takes control of a conversation, the AI can pause automatically to prevent conflicting responses.

Once the conversation returns to the automated flow, the AI can continue using the existing conversation and issue context.

---

## 🛠️ Tech Stack

**Automation & Orchestration**

* n8n
* Webhooks
* REST APIs

**AI**

* OpenAI
* AI Agents
* Text Classification
* Context-aware response generation

**Customer Service**

* Freshchat
* Freshdesk
* WhatsApp

**Data & State**

* Supabase
* Google Sheets
* Customer & Order APIs

---

## 📂 Repository Structure

```text
ai-customer-service-automation/
│
├── README.md
├── customer-service-main.json
└── department-resolution-flow.json
```

### `customer-service-main.json`

Main customer-service workflow responsible for:

* receiving Freshchat events
* processing customer messages
* managing conversation state
* AI customer support
* customer/order lookups
* image handling
* issue management
* Freshdesk ticket creation
* human-agent handoff logic

### `department-resolution-flow.json`

Resolution workflow responsible for:

* receiving Freshdesk updates
* identifying active issues
* classifying department responses
* generating customer-facing resolutions
* validating WhatsApp communication availability
* updating issue state
* triggering manual follow-up when required

---

## 🔐 Security & Privacy

This repository contains a **sanitized portfolio version** of the production workflows.

For security and confidentiality:

* API keys and access tokens were removed
* credentials were replaced with placeholders
* production endpoints were anonymized
* customer information was removed
* internal IDs were removed
* proprietary prompts and operational rules were simplified

The public workflows are intended to demonstrate the **system architecture, automation design, and engineering approach**, not expose production credentials or private business data.

---

## 🎯 Project Goal

The goal of this project was to build a customer service system where AI is not limited to answering FAQs, but can participate in the full operational support lifecycle:

**Understand → Collect → Validate → Escalate → Track → Resolve → Follow Up**

---
## 🖼️ Workflow Screenshots

### Main Workflow — Part 1
<img width="675" height="711" alt="image" src="https://github.com/user-attachments/assets/11529db9-7c40-409d-b2d1-07b960ca5382" /> 

### Main Workflow — Part 2
<img width="1074" height="574" alt="image" src="https://github.com/user-attachments/assets/44994fe8-79f6-4b60-9db9-b7334fb35ab6" />

### Main Workflow — Part 3
<img width="992" height="731" alt="image" src="https://github.com/user-attachments/assets/d382d874-84bd-475e-986c-fb272e77c239" />

### Department Resolution Workflow
<img width="1559" height="727" alt="image" src="https://github.com/user-attachments/assets/70ffe408-e395-47fc-9002-b49a682a9583" />

### Built by Yahya Zakaria

**AI Specialist | AI Agents | n8n Automation | Machine Learning**





