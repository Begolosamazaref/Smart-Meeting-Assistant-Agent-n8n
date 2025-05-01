# Smart-Meeting-Assistant-Agent-n8n-
Use n8n to build a smart agent that acts as a meeting assistant over Telegram, integrated with LLMs, file analysis, and calendar scheduling.
📅 Telegram to Calendar AI Workflow
This project is a Telegram-integrated meeting planner built using n8n, AI language models (via Groq), and Google Calendar + Gmail. It enables users to send a PDF via Telegram and have an AI agent:

Parse meeting details

Extract and summarize content (if a PDF is attached)

Create an event on Google Calendar

Summarize the simulated meeting

Send a summary via Gmail

🧠 Features
🔗 Telegram trigger to initiate the workflow

📄 Extract text from uploaded PDF

🧠 Use Groq to understand prompts or documents

📆 Automatically schedule meetings on Google Calendar

✉️ Send meeting summary via Gmail

📝 AI-generated simulated transcript and summary

🚀 How It Works
User sends a Telegram message or PDF file with meeting context.

The system determines if a file is attached:

If yes: extracts text from PDF.

If no: uses the message text.

The message (or PDF content) is formatted as input to an AI agent to generate structured meeting info.

Data is parsed into:

Date start

Date end

Meeting name

Details

Participants

A meeting is scheduled in Google Calendar with attendees.

A simulated transcript is created and summarized using AI.

A Gmail email is sent to participants with the meeting summary.

🛠 Requirements
n8n installed locally or on server (Docker)

API credentials for:

Telegram Bot

Groq API

Google Calendar OAuth

Gmail OAuth

Telegram Webhook URL properly configured

🧩 Nodes Used
Node Name	Type	Purpose
Telegram Trigger	telegramTrigger	Receive messages from Telegram
Code3	code	Preprocess input and binary data
Extract from File	extractFromFile	Read text from PDF
Code	code	Merge message & file data
Groq Chat Model1	lmChatGroq	AI for meeting content understanding
Generate Agenda1	agent	Create structured agenda from input
Code4	code	Parse AI output to extract fields
Schedule Meeting1	googleCalendar	Add meeting to Google Calendar
Code (Transcript)	code	Simulate a meeting transcript
Groq Chat Model	lmChatGroq	Summarize the transcript
Summarize Transcript1	agent	Shorten transcript using AI
Gmail1	gmail	Send meeting summary email

🔧 Setup Instructions
import this workflow JSON into your n8n instance.

Set up the following credentials in n8n:

Telegram Bot

Groq API

Google Calendar

Gmail

Configure your Telegram Bot with the correct webhook.

Enable the workflow in n8n.

Send a message or a PDF to your Telegram bot to trigger the workflow.




