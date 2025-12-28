# Flight Booking Optimizer – Weekly Build Plan

## Overview

This document outlines a week-by-week execution plan to build a **Flight Booking Optimizer** MVP.

The product recommends the **cheapest way to book a flight** by comparing:
- Standard cash fares  
- Airline miles redemptions  
- Buying miles during promotions  
- Credit card point transfers  

The tool is designed for **beginners** who do not understand miles or points.  
It provides **step-by-step booking instructions** instead of booking tickets directly.

### Initial Scope (MVP)
- One-way flights only  
- Economy class only  
- Routes between **India ↔ USA**  
- Recommendation-only (no booking)  
- Personal-use (no monetization)

---

## High-Level Architecture

1. **Cash Fare Engine**
   - Fetches cheapest cash price for a route and date.

2. **Points & Miles Engine**
   - Stores airline partners, award pricing rules, transfer ratios, and promos.

3. **Cost Engine**
   - Converts miles required into real-world cost.

4. **Recommendation Engine**
   - Ranks all booking methods and explains the cheapest path.

5. **Frontend UI**
   - Simple search form and beginner-friendly results page.

---

## Week-by-Week Execution Plan

---

## Week 1 – MVP Definition & Project Setup

### Goals
- Lock MVP scope
- Set up repository and base application

### Tasks
- Finalize MVP constraints:
  - One-way flights
  - Economy only
  - India ↔ USA routes
- Choose tech stack:
  - Frontend: Next.js + Tailwind
  - Backend: FastAPI (Python) or Next.js API routes
  - Database: Supabase (Postgres) or SQLite
- Create GitHub repository
- Create base pages:
  - Search page
  - Results page (placeholder)

### Deliverable
- App runs locally with a basic search UI

---

## Week 2 – Cash Fare Integration

### Goals
- Display real cash flight prices

### Tasks
- Integrate flight pricing API (choose one):
  - Amadeus Self-Service API
  - Kiwi (Tequila API)
- Create backend endpoint to fetch cheapest fare
- Return:
  - Airline
  - Price
  - Stops
  - Booking link (if available)
- Display cash option in results UI

### Deliverable
- End-to-end cash fare search working

---

## Week 3 – Loyalty Program Knowledge Base

### Goals
- Teach the system how airline programs work

### Programs to Start With
- Air Canada Aeroplan  
- United MileagePlus  
- British Airways / Qatar Avios  
- Flying Blue (Air France / KLM)

### Tasks
- Create data models for:
  - Loyalty programs
  - Airline alliances and partners
  - Transfer partners (Amex, Chase, Citi)
- Seed initial data into database or JSON config

### Deliverable
- System knows which programs apply to a route

---

## Week 4 – Award Pricing Engine (Estimates)

### Goals
- Estimate miles required for award tickets

### Tasks
- Implement award pricing function:
  - Input: program, route, date
  - Output: miles required, estimated taxes
- Use:
  - Distance-based pricing (Avios-style)
  - Typical award ranges for India ↔ USA
- Clearly mark results as **estimated**

### Deliverable
- Award options appear alongside cash fares

---

## Week 5 – Miles & Points Acquisition Cost Engine

### Goals
- Convert miles into real-world cost

### Acquisition Paths
1. Buy miles during promotions  
2. Transfer credit card points with bonuses  

### Tasks
- Implement cost calculation:
  - Buy miles → dollar cost
  - Transfer points → points required
- Apply:
  - Buy-miles promotions
  - Transfer bonuses
- Output effective total cost

### Deliverable
- Real cost comparison enabled

---

## Week 6 – Recommendation & Explanation Engine

### Goals
- Identify cheapest option and explain it clearly

### Tasks
- Rank options by total cost
- Select:
  - Best option
  - 2–3 alternatives
- Auto-generate step-by-step booking instructions:
  - Cash booking
  - Buying miles
  - Transferring points
  - Partner airline booking

### Deliverable
- Beginner-friendly “Cheapest Way to Book” output

---

## Week 7 – Award Availability (Light Version)

### Goals
- Help users verify award availability

### Tasks
- Add deep links to airline award search pages
- Add availability confidence labels:
  - Likely available
  - Verify manually
  - Unknown
- Provide clear instructions on how to check availability

### Deliverable
- User guidance for award verification

---

## Week 8 – UX & Beginner Education

### Goals
- Make the app usable by total beginners

### Tasks
- Add glossary tooltips:
  - Miles
  - Award ticket
  - Transfer bonus
- Add “What you need” checklist per option:
  - Required accounts
  - Time required
  - Promo expiration
- Improve mobile responsiveness

### Deliverable
- Beginner-proof UX

---

## Week 9 – Testing & Validation

### Goals
- Ensure recommendations work in real-world scenarios

### Tasks
- Test 15–20 real routes
- Validate pricing accuracy
- Add logging and error handling
- Handle API failures gracefully

### Deliverable
- Stable and reliable MVP

---

## Week 10 – Deployment & Maintenance

### Goals
- Make the tool usable anytime

### Tasks
- Deploy:
  - Frontend on Vercel
  - Backend on Render or Supabase
- Secure API keys
- Create workflow to update:
  - Buy-miles promotions
  - Transfer bonuses

### Deliverable
- Live personal-use Flight Booking Optimizer

---

## Future Enhancements

- User accounts with saved point balances
- Real-time award availability
- Price and promo alerts
- Multi-city itineraries
- Hotel booking optimization
- AI-based routing suggestions

---

## MVP Success Criteria

- User enters route and date  
- System shows cheapest booking method  
- User understands exactly how to book it  
- No prior miles knowledge required  
