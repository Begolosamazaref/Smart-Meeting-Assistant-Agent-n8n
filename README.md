# 📅 Telegram to Calendar AI Workflow

A Telegram-integrated meeting planner using [n8n](https://n8n.io/), [Groq](https://groq.com/), Google Calendar, and Gmail. Users can send a message or a PDF via Telegram, and the system will:

- Parse meeting details  
- Extract and summarize content from PDFs  
- Create Google Calendar events  
- Generate a simulated transcript  
- Send summaries via Gmail  

---

## 🧠 Features

- 🔗 Telegram Trigger to initiate the workflow  
- 📄 Extract text from uploaded PDF files  
- 🧠 Use Groq AI to understand meeting prompts or documents  
- 📆 Automatically schedule meetings on Google Calendar  
- ✉️ Send AI-generated meeting summaries via Gmail  
- 📝 Generate simulated transcripts and concise summaries  

---

## 🚀 How It Works

1. User sends a message or PDF file to the Telegram bot.
2. System checks if a file is attached:
   - 📎 **If PDF is attached** → Extracts text from the file.
   - ✉️ **If not** → Uses the message text.
3. Content is formatted and sent to the AI agent to generate structured meeting information.
4. Extracted data includes:
   - Start Date  
   - End Date  
   - Meeting Name  
   - Meeting Details  
   - Participants  
5. A Google Calendar event is created with the parsed data.
6. A simulated transcript is generated and summarized using Groq AI.
7. Gmail sends the summary to all participants.

---

## 🛠 Requirements

- [n8n](https://n8n.io/) installed locally or on a server (e.g. Docker)
- API Credentials for:
  - Telegram Bot
  - Groq API
  - Google Calendar OAuth
  - Gmail OAuth
- Telegram Webhook URL properly configured

---

## 🧩 Nodes Used

| Node Name               | Type              | Purpose                                    |
|------------------------ |------------------ |--------------------------------------------|
| Telegram Trigger        | `telegramTrigger` | Receive messages from Telegram             |
| Code3                   | `code`            | Preprocess input and binary data           |
| Extract from File       | `extractFromFile` | Read text from uploaded PDF                |
| Code                    | `code`            | Merge Telegram message and file content    |
| Groq Chat Model1        | `lmChatGroq`      | Understand and parse meeting content       |
| Generate Agenda1        | `agent`           | Generate a structured meeting agenda       |
| Code4                   | `code`            | Parse AI output to extract relevant fields |
| Schedule Meeting1       | `googleCalendar`  | Add event to Google Calendar               |
| Code (Transcript)       | `code`            | Simulate a meeting transcript              |
| Groq Chat Model         | `lmChatGroq`      | Summarize the transcript                   |
| Summarize Transcript1   | `agent`           | Shorten transcript using AI                |
| Gmail1                  | `gmail`           | Send meeting summary to attendees          |

---

## 🔧 Setup Instructions

1. Import the workflow JSON into your **n8n** instance.
2. Set up the following **credentials** inside n8n:
   - Telegram Bot
   - Groq API
   - Google Calendar
   - Gmail
3. Configure your Telegram Bot with the proper **Webhook URL**.
4. Enable the workflow in n8n.
5. Send a message or a PDF to your Telegram bot to trigger the workflow.

---


