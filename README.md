# Flight Booking Optimizer – Weekly Build Plan

## Overview

This document outlines a week-by-week execution plan to build a **Flight Booking Optimizer** MVP.  
The product recommends the **cheapest way to book a flight** by comparing:

- Standard cash fares  
- Airline miles redemptions  
- Buying miles during promotions  
- Credit card point transfers  

The tool is designed for **beginners** who do not understand miles or points, and it provides **step-by-step booking instructions** instead of booking tickets directly.

Initial focus:
- One-way flights
- Economy class
- Routes between **India ↔ USA**
- Personal-use MVP (no monetization)

---

## High-Level Architecture

1. **Cash Fare Engine**
   - Fetches cheapest cash price for a route/date.

2. **Points & Miles Engine**
   - Knows airline partners, award pricing models, transfer ratios, and promos.

3. **Cost Engine**
   - Converts miles required → real-world cost (buy miles or transfer points).

4. **Recommendation Engine**
   - Ranks all booking methods and explains the cheapest path.

5. **Frontend UI**
   - Simple search form + beginner-friendly results page.

---

## Week-by-Week Plan

---

## Week 1 – MVP Definition & Project Setup

**Goals**
- Lock MVP scope
- Set up repo and base app

**Tasks**
- Finalize MVP constraints:
  - One-way flights
  - Economy only
  - India ↔ USA routes
- Choose tech stack:
  - Frontend: Next.js + Tailwind
  - Backend: FastAPI (Python) or Next.js API routes
  - DB: Supabase / Postgres or SQLite
- Create GitHub repo
- Create base pages:
  - `/search`
  - `/results` (placeholder)

**Deliverable**
- App runs locally with search UI scaffold

---

## Week 2 – Cash Fare Integration

**Goals**
- Show a real cash price for a flight

**Tasks**
- Integrate flight pricing API (choose one):
  - Amadeus Self-Service API
  - Kiwi (Tequila API)
- Backend endpoint:
