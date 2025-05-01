# Smart-Meeting-Assistant-Agent-n8n-
Use n8n to build a smart agent that acts as a meeting assistant over Telegram, integrated with LLMs, file analysis, and calendar scheduling.

📅 Telegram to Calendar AI Workflow
A Telegram-integrated meeting planner using n8n, Groq AI, Google Calendar, and Gmail. Users can send a message or a PDF via Telegram, and the system will:

Parse meeting details

Extract & summarize content from PDFs

Create Google Calendar events

Generate a simulated transcript

Send summaries via Gmail

🧠 Key Features
🔗 Telegram Trigger: Start workflow via Telegram message or PDF

📄 PDF Text Extraction: Read meeting context from uploaded files

🧠 Groq AI Integration: Interpret prompts or documents intelligently

📆 Google Calendar Integration: Auto-schedule meetings

✉️ Gmail Integration: Send meeting summaries

📝 Simulated Transcript: AI-generated transcript and summary

🚀 How It Works
User sends a message or PDF to the Telegram bot.

The system checks:

📎 If a PDF is attached → extract text.

✉️ If no PDF → use the message text.

The input is formatted and sent to the AI for processing.

AI extracts:

Start Date

End Date

Meeting Name

Details

Participants

Google Calendar schedules the event with attendees.

AI generates a simulated transcript and summary.

Gmail sends the summary email to participants.

🛠 Requirements
✅ n8n installed (locally or via Docker)

🔐 API Credentials for:

Telegram Bot

Groq API

Google Calendar OAuth

Gmail OAuth

🌐 Telegram Webhook URL configured properly

🧩 Nodes Used in Workflow
Node Name	Type	Purpose
Telegram Trigger	telegramTrigger	Receive Telegram messages
Code3	code	Preprocess input and binary data
Extract from File	extractFromFile	Extract text from PDFs
Code	code	Merge message and file data
Groq Chat Model1	lmChatGroq	Understand meeting content via AI
Generate Agenda1	agent	Generate structured agenda
Code4	code	Parse AI output to extract fields
Schedule Meeting1	googleCalendar	Schedule meeting on Google Calendar
Code (Transcript)	code	Simulate a meeting transcript
Groq Chat Model	lmChatGroq	Summarize the simulated transcript
Summarize Transcript1	agent	Final summary generation
Gmail1	gmail	Send meeting summary via email

🔧 Setup Instructions
Import the workflow JSON into your n8n instance.

Set up the following credentials in n8n:

Telegram Bot

Groq API

Google Calendar

Gmail

Configure your Telegram bot with the appropriate webhook URL.

Enable the workflow in n8n.

Trigger the workflow by sending a message or a PDF to your Telegram bot.




