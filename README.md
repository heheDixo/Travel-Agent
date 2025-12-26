# 🧳 End-to-End Travel Agent (Pure Python)

A **framework-independent, end-to-end AI Travel Agent** built using **pure Python**.  
The agent understands user intent, plans trips intelligently, and fetches **real-time data** using external APIs — without relying on LangChain, AutoGen, or other agent frameworks.

This project demonstrates **core agent engineering fundamentals**, clean architecture, and real-world API integration.

---

## ✨ Key Highlights

- 🧠 LLM-powered intent understanding
- 🧩 Multi-agent architecture (Reasoning + Tools)
- 🔌 Real-time data integration (Flights, Hotels, Activities)
- 🧱 Framework-independent (Pure Python)
- 🔄 Mock → Real API upgrade path
- 📦 Structured & deterministic output
- 🧪 Easy to test, debug, and extend

---

## 🏗️ Architecture Overview
User Input
   ↓
Intent Agent (LLM)
   ↓
Planner Agent
   ↓
┌────────────┬────────────┬────────────┐
│ FlightAgent│ HotelAgent │ActivityAgent│   ← reasoning only
└────────────┴────────────┴────────────┘
   ↓
┌────────────┬────────────┬────────────┐
│ FlightTool │ HotelTool  │ActivityTool│   ← real-time tools
└────────────┴────────────┴────────────┘
   ↓
External APIs (Amadeus, Booking.com, Wikipedia)

Agents **never fetch data directly**.  
Tools **never perform reasoning**.

---

## 🧠 Why Pure Python?

This project avoids agent frameworks intentionally to showcase **fundamental agent design skills**.

### Benefits
- Full control over execution flow
- No hidden abstractions
- Easier debugging
- No vendor lock-in
- Interview-friendly design
- Clean separation of concerns

> Frameworks can be added later.  
> Architecture cannot.

---

## 🌐 APIs Used (V2)

### ✈️ Flights — **Amadeus API**
- Official airline data provider
- Real-time flight prices
- Industry-standard travel API

🔗 https://developers.amadeus.com

---

### 🏨 Hotels — **Booking.com API (via RapidAPI)**
- Booking.com hotel data
- Free tier available
- Easy integration for MVPs

🔗 https://rapidapi.com/apidojo/api/booking-com/

---

### 🗺️ Activities — **Wikipedia REST API**
- Free & open
- No API key required
- Legal and stable source

🔗 https://en.wikipedia.org/api/rest_v1

---

## 📦 Output Format (Stable Schema)

The agent always returns a structured travel plan:

```json
{
  "trip_summary": {...},
  "selected_flight": {...},
  "selected_hotel": {...},
  "activities": [...],
  "cost_breakdown": {...},
  "assumptions": [...]
}
