Live Chat Bot with Google ADK

A powerful, AI-driven YouTube Live Chat bot that acts as your personal moderator and engagement assistant. Built with Google's Agent Development Kit (ADK) and Gemini models, it seamlessly integrates with your stream to interact with viewers in real-time.

## 🌟 Features

*   **🤖 AI-Powered Persona**: Acts as *you* (the streamer), answering questions based on your profile.
*   **🎮 Gaming Integration**:
    *   **Valorant Stats**: Fetches real-time rank, MMR, and match history (e.g., \"!rank\", \"!lastmatch\").
    *   **Game Awareness**: Knows what game you are playing and adapts its responses.
*   **🗣️ Multilingual Support**: Automatically detects and responds in **English**, **Hindi**, and **Hinglish**.
*   **🔍 Smart Search**: Uses Google Search to answer factual questions (weather, news, how-to).
*   **🛡️ Moderation**: Filters spam, welcomes new viewers, and keeps the chat engaging.
*   **⚙️ Easy Setup**: Interactive first-time setup to customize the bot for your stream.

---

## 🚀 Quick Start Guide

### Prerequisites

1.  **Python 3.10+**: Ensure Python is installed.
2.  **Google Cloud Project**: You need a project with **YouTube Data API v3** enabled.
3.  **API Keys**:
    *   **Google AI API Key** (for Gemini models).
    *   **YouTube Data API Key** (for reading/posting to chat).

### 🔑 How to Get API Keys

#### 1. Google AI API Key (Gemini)
1.  Go to [Google AI Studio](https://aistudio.google.com/).
2.  Click on **"Get API key"** in the top left.
3.  Click **"Create API key"**.
4.  Copy the key string (starts with `AIza...`).

#### 2. YouTube OAuth Credentials (client_secret.json)
*Required for the bot to post messages to your chat.*
1.  Go to the [Google Cloud Console Credentials page](https://console.cloud.google.com/apis/credentials).
2.  Click **"Create Credentials"** > **"OAuth client ID"**.
3.  **Application type**: Select **"Desktop app"**.
4.  **Name**: Enter a name (e.g., "YouTube Chat Bot").
5.  Click **"Create"**.
6.  Download the JSON file (click the download icon ⬇️).
7.  **Rename** the downloaded file to `client_secret.json`.
8.  **Move** this file into the `app` folder of the project.

#### 3. Valorant API Key (Optional)
*Required only if you want to use Valorant stats commands like `!rank`.*
1.  Go to the [HenrikDev Dashboard](https://api.henrikdev.xyz/dashboard).
2.  Login with Discord.
3.  Copy your **API Key** (starts with `HDEV-`).

### Step 1: Clone & Install

```powershell
# Clone the repository
git clone <your-repo-url>
cd Youtube-Streaming-Chat-Bot

# Create a virtual environment (Recommended)
python -m venv .venv
.\.venv\Scripts\activate.ps1

# Install dependencies
pip install -r requirements.txt
```

### Step 2: Configuration

1.  Navigate to the `app` directory:
    ```powershell
    cd app
    ```
2.  Create a new file named `.env` inside the `app` folder.
3.  Copy and paste the following content into your new `.env` file, replacing the placeholders with your actual keys:

    ```env
    # Google AI API Key (Get from Google AI Studio)
    GOOGLE_API_KEY=your_google_ai_key_here
    
    # YouTube API Key (Get from Google Cloud Console)
    YOUTUBE_API_KEY=your_youtube_api_key_here
    
    # Valorant API Key (Optional - Get from HenrikDev)
    HENRIK_DEV_API_KEY=your_hdev_key_here
    
    # Optional: Set a default video ID (or provide it when running)
    YOUTUBE_VIDEO_ID=
    
    # Agent Configuration
    AGENT_NAME=youtube_chat_advanced
    ```

### Step 3: Run the Bot

Start the bot using the runner script:

```powershell
python run_youtube_bot.py
```

---

## 🛠️ First-Time Setup

When you run the bot for the first time, it will guide you through a setup process to personalize the AI:

1.  **Stream Type**: Are you a gaming streamer or a variety/coding streamer?
2.  **Profile Details**:
    *   **Name**: Your streamer name.
    *   **Game Info**: If you play Valorant, you can add your ID (Name#Tag) for stat commands.
    *   **Bio**: A short description of what you do (optional).
    *   **System Specs**: Your PC specs (optional).

*Note: You can skip optional fields by pressing Enter.*

### Daily Usage

Every time you run the bot, it will ask for the current context:
*   **Gamers**: \"What game are you playing today?\"
*   **Others**: \"What is the topic of today's stream?\"

This ensures the AI always knows the context of your live stream!

---

## 🎮 Valorant Commands

If you provided your Valorant ID during setup, viewers can use these commands in chat:

*   `!rank` - Shows your current rank and ELO.
*   `!stats` - Displays K/D ratio and win rate.
*   `!lastmatch` - Shows details of your last game (Agent, KDA, Score).

---

## 📂 Project Structure

```
adk-streaming/
├── app/
│   ├── run_youtube_bot.py           # Main entry point
│   ├── streamer_profile.json        # Your saved profile (auto-generated)
│   ├── .env                         # API keys and config
│   ├── tools/                       # Custom tools (Valorant, etc.)
│   ├── youtube_chat_advanced/       # The AI Agent logic
│   └── youtube_integration/         # YouTube API handling
├── requirements.txt                 # Python dependencies
└── README.md                        # This guide
```

## ⚠️ Important Notes

*   **Quota Limits**: The YouTube Data API has a daily quota. The bot is optimized to use minimal quota for reading (using `pytchat`), but posting messages consumes quota (50 units/msg).
*   **Security**: Never share your `.env` file or API keys publicly.

## 🤝 Contributing

Feel free to open issues or submit pull requests to improve the bot!

---
*Happy Streaming!* 🎥✨''')
