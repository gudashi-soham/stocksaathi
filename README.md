
🛍️ StockSaathi

Bol do, stock update ho jayega.

StockSaathi is a simple inventory assistant for local shopkeepers (kirana stores). Instead of learning complex software, the shopkeeper just sends a normal WhatsApp-style text or voice message in Hinglish, for example:

"Aaj 20 Maggi aali, 8 bikli, 12 remaining"

The system turns this message into structured stock data, checks it, updates inventory, and shows everything on a live dashboard with one-click PDF reports.

The Problem

Local shopkeepers often find conventional inventory software hard to use. Their daily stock updates already happen naturally, as short text messages or voice notes. There is no simple tool that understands this way of working.

Our Solution

A shopkeeper sends a message the way they normally talk. StockSaathi:

Receives the text or voice note
Converts voice to text (voice only)
Uses AI to extract product, quantity and transaction type
Validates the result before saving
Updates stock automatically
Shows live inventory, alerts and reports on a web dashboard
Example
Input	Extracted data
"Aaj 20 Maggi aali, 8 bikli, 12 remaining"	Maggi: purchase 20, sale 8, stock count 12

The system also reconciles the numbers (opening stock + purchases − sales should match the stated count) and asks the shopkeeper to confirm when something doesn't add up.

Features

In the current prototype

📊 Dashboard with total, in-stock, low-stock and out-of-stock counts
⚠️ "Needs your attention" alerts for low and finished items
💬 WhatsApp-style chat demo for text (and browser voice input where supported)
🧠 Hinglish message understanding (mock, rule-based) with confidence scores
✅ Confidence routing: auto-save, ask to confirm, or ask again
🧾 Transaction history of purchases, sales and adjustments
📄 One-click PDF stock report
📱 Simple, mobile-friendly UI

Planned (see Roadmap)

Real WhatsApp Business / Cloud API integration
Gemini-based structured extraction
Indian-language speech-to-text (Sarvam or Whisper)
PostgreSQL database and Flask backend
Automated daily stock report on WhatsApp
How It Works
WhatsApp / SMS
      ↓
Webhook / Message Receiver
      ↓
Backend API
      ↓
Speech-to-Text (voice only)
      ↓
AI/NLP Extraction  →  Structured JSON
      ↓
Validation + Confidence check
      ↓
Inventory Database
      ↓
Web Dashboard + PDF Report
      ↓
Optional WhatsApp Report Reply
Confidence routing
Result	What happens
High confidence, all checks pass	✓ Saved automatically
Medium confidence or stock mismatch	❓ Bot asks the shopkeeper to confirm (Yes / No)
Low confidence or unknown product	✕ Bot asks the shopkeeper to send it again

AI output is never saved without validation.

Tech Stack

Current prototype (frontend)

React + TypeScript
Tailwind CSS + shadcn/ui
Recharts (charts)
jsPDF (PDF reports)
Built with Lovable

Planned full system

Layer	Technology
Backend	Python + Flask
Database	PostgreSQL
Messaging	WhatsApp Business / Cloud API
AI extraction	Gemini with structured JSON output
Validation	Pydantic + fuzzy product matching (rapidfuzz)
Speech-to-text	Sarvam or Whisper
PDF	Python PDF library (e.g. ReportLab)
