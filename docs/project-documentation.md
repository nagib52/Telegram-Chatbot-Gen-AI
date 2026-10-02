# Project Documentation

## Overview

This repository contains a Telegram chatbot powered by OpenAI. The bot is built with `aiogram`, receives messages from Telegram users, forwards them to OpenAI's ChatGPT API, and returns generated responses back to the user.

## Components

- `main.py`: The primary bot implementation.
- `requirements.txt`: Python dependencies.
- `Dockerfile`: Optional containerization setup.
- `Assets/`: Visual assets and architecture diagrams.
- `docs/`: Project documentation.
- `workflows/`: Mermaid workflow diagrams describing the bot and deployment flow.

## How it Works

1. A user sends a message to the Telegram bot.
2. Telegram forwards the update to the bot application.
3. The bot processes the message and optionally maintains a short context history.
4. The bot sends the user message to OpenAI's ChatGPT API.
5. OpenAI returns a text response.
6. The bot sends the response back to the Telegram chat.

## Installation

### Standard setup

```powershell
python -m pip install -r requirements.txt
```

### Optional UV setup

If you prefer a faster package manager, install `uv` and use it to set up dependencies.

```powershell
python -m pip install uv
uv install -r requirements.txt
```

## Configuration

Create a `.env` file in the repository root with the following values:

```ini
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
TELEGRAM_BOT_TOKEN=xxxxxxxxxx:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## Running the Bot

```powershell
python main.py
```

Use `/start`, `/help`, or `/clear` to interact with the bot through Telegram.

## Docker Deployment

Build and run the Docker image:

```powershell
docker build -t telegram-telebot .

docker run --rm -e OPENAI_API_KEY=****** -e TELEGRAM_BOT_TOKEN=******** telegram-telebot
```

## Developer Notes

- The bot stores the last OpenAI response in a simple `Reference` object, which enables repeatable follow-up context.
- The project is intentionally minimal and can be extended with additional command handlers, persistent storage, or multi-user session handling.
- Use the `workflows/` folder for architecture and runtime diagrams.

## Recommended Improvements

- Add secure secret management for production deployment.
- Persist conversation context to a database.
- Add automated tests for command handlers and OpenAI integration.
- Add GitHub Actions workflows for CI.
