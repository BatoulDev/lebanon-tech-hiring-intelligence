# 🇱🇧 Lebanon Tech Hiring Intelligence

An automation-driven intelligence system designed to map, structure, and monitor the Lebanese tech ecosystem.

---

## 🚀 Overview

Lebanon Tech Hiring Intelligence is a structured data pipeline built with n8n to collect, clean, deduplicate, and maintain an up-to-date database of tech companies in Lebanon.

---

# 🧩 Phase 1 — Company Intelligence Engine

### 🎯 Objective
Build a stable ingestion system that continuously collects and maintains structured data about Lebanese tech companies.

---

## ⚙️ Workflow Architecture

1. Trigger workflow manually in n8n
2. Run Apify Google Maps Scraper Actor
3. Normalize and structure company data
4. Generate a deterministic `unique_key`
5. Process companies sequentially
6. Check if company already exists in Google Sheets
7. If exists → Update row
8. If not → Append new row

---

## 🛠 Tech Stack

- n8n (Cloud)
- Apify (Google Maps Scraper Actor)
- Google Sheets API
- Conditional Logic (IF Nodes)
- Split in Batches
- Wait Node

---

# 🧠 Phase 2 — LinkedIn & Hiring Detection Engine

- Extract LinkedIn URL from company data.
- Run Actor (Apify – LinkedIn Scraper Actor).
- Get Dataset Items (retrieve posts & job listings).
- Keyword-based hiring detection (hiring, internship, junior, trainee, apply now).
- Generate `hiring_status` and `internship` flags.
- Compare with previous hiring status in Google Sheets.

---

# 🔔 Phase 3 — Notification & Intelligence Alerts

- IF logic to detect new hiring activity (status changed from NO to YES).
- Telegram Node to send real-time alert.
- Optional: AI summarization before notification.
- Maintain hiring history tracking.

---

## 👩‍💻 Author

Batoul Dev  
AI & Automation Systems Builder
