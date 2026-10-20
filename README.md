# 🤖 AI-Powered FAQ Chatbot | n8n + Google Gemini

An AI-powered FAQ chatbot built using **n8n, Google Gemini, and Google Sheets** to answer customer questions for Thread & Co., a fictional online fashion store. The workflow retrieves relevant FAQ information, generates conversational responses, and logs customer interactions in Google Sheets.

## 📌 Overview

This project demonstrates how to build an AI-powered customer support workflow using low-code automation. The chatbot accepts questions through a chat interface, uses Google Gemini to generate responses, and retrieves business information from a Google Sheets FAQ database.

It also records customer questions and bot responses in a separate sheet for interaction tracking.

## ✨ Features

- 💬 **Conversational Interface** — Accepts customer questions through the n8n chat interface.
- 🧠 **AI-Powered Responses** — Uses Google Gemini to generate natural-language answers.
- 📚 **FAQ Knowledge Base** — Retrieves store information from Google Sheets.
- 🛡️ **Grounded Responses** — Instructs the AI to avoid inventing prices, availability, delivery dates, and store policies.
- 📊 **Conversation Logging** — Stores timestamps, user questions, session IDs, bot responses, and response sources in Google Sheets.
- ⚙️ **Workflow Automation** — Connects the chat trigger, AI agent, language model, and Sheets integrations in a single workflow.

## 🏗️ Workflow Architecture

The workflow follows this process:

1. **Customer Chat Trigger** — Receives a message from the user.
2. **FAQ Assistant Agent** — Processes the question and coordinates the response.
3. **Gemini LLM** — Generates a natural-language answer.
4. **Retrieve FAQ Knowledge Base** — Retrieves relevant information from the Google Sheets FAQ database.
5. **Log Customer Conversations** — Appends the interaction details to the chat log sheet.

The Gemini model and FAQ lookup are connected to the AI Agent as model and tool inputs, respectively.

## 🖼️ Workflow

### 1. Architecture

A visual overview of the n8n workflow and its connected nodes.

![AI-Powered FAQ Chatbot Workflow](media/workflow.png)

### 2. Chatbot Interaction 

An example of the chatbot responding to a customer question.

![FAQ Chatbot Interaction 1](media/chat1.png)

![FAQ Chatbot Interaction 2](media/chat2.png)

### 4. Activity Log

A view of the logged chatbot activity and interaction records.

![FAQ Chatbot Activity Log](media/activity%20log.png)

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| [n8n](https://n8n.io/) | Workflow automation and orchestration |
| [Google Gemini](https://ai.google.dev/) | AI-powered response generation |
| [Google Sheets](https://sheets.google.com/) | FAQ knowledge base and conversation logging |
| JSON | Workflow export and configuration |
| GitHub | Version control and project documentation |

## ⚙️ Setup and Configuration

### Prerequisites

- An n8n instance, either local or hosted.
- A Google Gemini API key.
- A Google account with access to Google Sheets.
- A Google Sheets spreadsheet containing the FAQ data and a separate sheet for conversation logs.

### Step 1: Import the Workflow

1. Clone or download this repository.
2. Open your n8n instance.
3. Import the sanitized workflow JSON file into n8n.
4. Open the imported workflow and review the node configuration.

### Step 2: Configure Google Gemini

1. Create an API key through [Google AI Studio](https://aistudio.google.com/apikey).
2. Add your Gemini credentials in n8n.
3. Select the appropriate credentials in the Google Gemini Chat Model node.
4. Choose a model currently supported by your account.

### Step 3: Configure Google Sheets

1. Connect your Google Sheets account through n8n credentials.
2. Select your FAQ spreadsheet in the **Retrieve FAQ Knowledge Base** node.
3. Select the appropriate FAQ worksheet.
4. Configure the **Log Customer Conversations** node to use the same spreadsheet and the worksheet intended for chat logs.
5. Verify that the column names match the workflow's field mappings.

The chat log sheet should contain these columns:

- `Timestamp`
- `User ID`
- `User Question`
- `Bot Response`
- `Response Source`

### Step 4: Test the Workflow

1. Save the workflow.
2. Open the n8n chat interface.
3. Ask a question about Thread & Co.
4. Verify that the response is based on the FAQ data.
5. Check the chat log worksheet to confirm that the interaction was recorded.

## 💬 Example Questions

Try these questions to test the chatbot:

- What products do you sell?
- Can you tell me more about your shirts and trousers?
- Do you offer casual wear for everyday use?
- What should I check before choosing a product from Thread & Co.?

The responses depend on the information available in the configured FAQ database.


## 🎯 Learning Outcomes

This project explores:

- Building AI-powered workflows with n8n.
- Integrating an LLM into an automation workflow.
- Connecting Google Sheets as a knowledge source.
- Designing prompts for grounded customer support responses.
- Logging interactions for tracking and analysis.
- Managing workflow exports and project documentation with GitHub.
