📘 E-Dentis_realtime — Realtime Voice AI Agent for Dental Clinics
E-Dentis_rentime is a production-grade realtime voice AI agent for dental clinics.
Powered by Gemini Live API, it supports natural, bilingual (Arabic/English) voice conversations
for appointment booking, patient support, FAQs, and real clinic workflows.

The project includes:

Full voice engine

Realtime streaming pipeline

LLM agent layer

Tool-calling

PMS integration

Analytics dashboard

Developer console

A fully modular, scalable, customizable solution for real-world clinics.

🚀 Features
🎤 Realtime Voice Assistant
Ultra-low-latency Gemini Live responses

16 kHz PCM streaming

High-quality AI speech

Arabic + English support

Automatic language detection

📅 Smart Appointment Handling
Book / modify / cancel appointments

Phone, name, service validation

Dentist suggestions

PMS integration (mock or real)

🧠 Agent Intelligence Layer
Dynamic system prompts

Tool-calling integration

Conversation manager

Safety filters

🎛 Simple Voice Console
Start/End session

Audio levels

Microphone control

Realtime logs

AR/EN hints

📊 Advanced Analytics Dashboard
Session metrics

Latency, hallucination, success rates

Realtime logs

Sentiment analysis

Tool usage

Altair chart support

🧰 Developer Console
Full LLM logs

Tool call inspector

Streaming event timeline

🏗 Architecture Overview
pgsql
نسخ الكود
E-Dentis_realtime/
│
├── src/
│   ├── components/
│   │   ├── simple-voice/
│   │   ├── dashboard/
│   │   ├── logger/
│   │   ├── settings/
│   │   └── side-panel/
│   │
│   ├── contexts/
│   ├── hooks/
│   ├── lib/
│   ├── ai/
│   ├── services/
│   ├── App.tsx
│   └── index.tsx
│
├── server/
│   ├── db.ts
│   ├── dbBookingIntegration.ts
│   ├── pmsIntegration.ts
│   ├── analytics-engine.js
│   └── security.ts
│
├── prisma/
│   ├── schema.prisma
│   ├── migration_lock.toml
│   └── seed.ts
│
├── public/
├── package.json
├── tsconfig.json
└── README.md
⚙️ Installation
1️⃣ Install dependencies
bash
نسخ الكود
npm install
2️⃣ Database Setup
bash
نسخ الكود
npx prisma migrate deploy
npx prisma db seed
3️⃣ Create .env file
Create a new file named .env:

ini
نسخ الكود
GEMINI_API_KEY=your_google_key
DATABASE_URL=postgresql://user:password@host:port/db
PMS_PROVIDER_KEY=mock
JWT_SECRET=your_jwt_secret
ANALYTICS_MODE=enabled
GOOGLE_APPLICATION_CREDENTIALS=./app-setting.json
🔐 Google Service Account Setup (Required)
This project uses Google Cloud services (Gemini API, realtime, etc.).
To authenticate securely, you must add your own app-setting.json file.

⚠️ This file is NOT included because it contains private keys.
Each developer must generate their own.

1. Create a Google Service Account
Open Google Cloud Console:
https://console.cloud.google.com/iam-admin/serviceaccounts

Click Create Service Account

Name it (example: e-dentist-agent)

Assign role → Editor

Save

2. Generate the key
Open the service account

Go to the Keys tab

Click Add Key → Create New Key → JSON

Download the JSON

Rename it:

pgsql
نسخ الكود
app-setting.json
Place it in project root:

bash
نسخ الكود
/E-Dentis_realtime/app-setting.json
3. Update .env
Make sure .env contains:

ini
نسخ الكود
GOOGLE_APPLICATION_CREDENTIALS=./app-setting.json
4. Ensure it's ignored
Your .gitignore MUST include:

markdown
نسخ الكود
app-setting.json
*.key
*.pem
▶️ Running the App
bash
نسخ الكود
npm run dev
Open in browser:

arduino
نسخ الكود
http://localhost:3000
🧪 Usage
Start voice session
Click Start Session and speak in Arabic or English.

Example commands:
css
نسخ الكود
Book a cleaning appointment for Sunday at 2 PM.
نسخ الكود
أجّل موعدي للساعة 4.
vbnet
نسخ الكود
Show me appointments by day.
🛠 Tech Stack
React + TypeScript

Gemini Live API

WebRTC / PCM 16k

Prisma ORM

Node.js backend

PostgreSQL

Altair / Vega

Zustand

SCSS

📈 Roadmap
 Mobile layout

 WhatsApp voice integration

 Real PMS support

 Multi-agent mode

 Export transcripts

 Customizable voice profiles

 Fine-tuned dental assistant model

🐞 Common Issues
❌ Microphone blocked
→ Allow browser mic permissions

❌ No AI response
→ Invalid GEMINI_API_KEY
→ Gemini Live API not enabled

❌ Failed booking
→ Prisma migration missing
→ Database not connected

❌ Audio lag
→ Slow network
→ VPN issues
→ Wrong PCM rate

📄 License
MIT License. Free for personal and commercial use.
