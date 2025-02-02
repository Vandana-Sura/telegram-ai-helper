# telegram-ai-helper
# Telegram AI Chatbot

This project implements a Telegram bot powered by AI for performing user registration, Gemini AI chat interactions, file analysis, and web search using Google Custom Search API. The bot integrates MongoDB for data storage and provides rich interactions through Pyrogram.

## Features

1. **User Registration**
   - Collects and stores user details (e.g., username, phone number) in MongoDB.
   - Asks for a phone number via Telegram's contact sharing feature.

2. **Gemini AI Chat**
   - Processes user queries using Google's Gemini AI model.
   - Stores queries and responses in MongoDB.

3. **Image and File Analysis**
   - Uses OCR (via Tesseract) to extract text from images.
   - Analyzes image and file content using AI and stores metadata in MongoDB.

4. **Web Search**
   - Searches the web using Google Custom Search API.
   - Provides top search results with summaries and links.
   - Logs search queries and results in MongoDB.

## Prerequisites

Before running the bot, ensure you have the following installed:

- Python 3.8+
- MongoDB (local or cloud instance)
- [Pyrogram](https://docs.pyrogram.org/)
- Tesseract OCR

## Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/your-repo/telegram-ai-bot.git
   cd telegram-ai-bot
   ```

2. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

3. **Set up MongoDB**:
   - Create a database and collections (`users`, `chat_history`, `file_analysis`).
   - Update the `MONGO_URI` in the code with your MongoDB credentials.

4. **Configure Tesseract**:
   - Install Tesseract OCR ([installation guide](https://github.com/tesseract-ocr/tesseract)).

5. **Set up environment variables**:
   Create a file named `config.py` and add the following variables:
   ```python
   API_ID = "<your_telegram_api_id>"
   API_HASH = "<your_telegram_api_hash>"
   BOT_TOKEN = "<your_telegram_bot_token>"
   GOOGLE_API_KEY = "<your_google_api_key>"
   MONGO_URI = "<your_mongo_uri>"
   DB_NAME = "<your_database_name>"
   GOOGLE_CSE_ID = "<your_google_cse_id>"
   GOOGLE_CLOUD_ID = "<your_google_cloud_id>"
   ```

## Running the Bot

1. Start the bot:
   ```bash
   python bot.py
   ```

2. Open your Telegram app and search for your bot using its username. Start a conversation to test the features.

## Commands

- `/start` - Registers a user and asks for their phone number.
- `/gem <prompt>` - Generates a response from the Gemini AI model.
- `/websearch <query>` - Performs a web search and returns top results.
- Upload a photo/document - Analyzes the content and provides insights.

## File Structure

```
telegram-ai-bot/
├── bot.py                 # Main bot script
├── requirements.txt       # Python dependencies
├── config.py              # Configuration file for credentials
└── README.md              # Project documentation
```

## Dependencies

- `pymongo`: For MongoDB integration.
- `pyrogram`: Telegram bot framework.
- `pytesseract`: OCR for extracting text from images.
- `google-generativeai`: To interact with Gemini AI.
- `requests`: For API requests.
