# Telegram GenAI Chatbot

![Python](https://img.shields.io/badge/Python-3.8%2B-blue.svg)
![Telegram](https://img.shields.io/badge/Telegram-Bot-blue.svg)
![OpenAI](https://img.shields.io/badge/OpenAI-API-blue.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

A lightweight Telegram chatbot built with `aiogram` and OpenAI’s ChatGPT API. This repository demonstrates a minimal, production-ready structure for a Telegram bot using environment configuration, optional Docker deployment, and clear developer documentation.

> Note: An architecture overview image is included below to help visualize the bot flow.

## Features

- Telegram bot using `aiogram`
- ChatGPT-style response generation via `openai`
- Context-managed response memory
- `/start`, `/help`, and `/clear` commands
- `.env` configuration for secrets
- Optional Docker deployment
- Optional `uv` package manager setup for faster dependency installation

## Architecture Overview

![Project Architecture](Assets/45454%20(1).png)

## Getting Started

### Requirements

- Python 3.8 or newer
- Telegram bot token from BotFather
- OpenAI API key

### Install dependencies

```powershell
python -m pip install -r requirements.txt
```

### Optional: install with UV package manager

`uv` can be significantly faster than pip for project setup.

```powershell
python -m pip install uv
uv install -r requirements.txt
```

> If you already have `uv` configured for your project, running `uv install` in the repository root will install the required packages.

## Configuration

Create a `.env` file in the project root with the following values:

```ini
OPENAI_API_KEY=sk-xxxxxxxxxxxxxxxxxxxxxxxxxxxxx
TELEGRAM_BOT_TOKEN=xxxxxxxxxx:xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
```

## Run the Bot

```powershell
python main.py
```

Then open your bot in Telegram and send a message to receive responses from the OpenAI-powered chat assistant.

## Docker Support

### Build image

```powershell
docker build -t telegram-telebot .
```

### Run container

```powershell
docker run --rm -e OPENAI_API_KEY=****** -e TELEGRAM_BOT_TOKEN=******** telegram-telebot
```

## Project Structure

```text
.
├── Assets/
│   └── 45454 (1).png
├── Dockerfile
├── LICENSE
├── README.md
├── docs/
│   └── project-documentation.md
├── main.py
├── requirements.txt
├── workflows/
│   ├── architecture-flow.md
│   ├── deployment-flow.md
│   └── runtime-flow.md
└── .env
```

## Documentation

Additional project documentation is available in the `docs/` folder. Workflow diagrams are available in `workflows/`.

## Telegram Bot Commands

- `/start` - start the bot conversation
- `/help` - display help instructions
- `/clear` - clear the bot context cache

## Notes

- Keep your API keys secure and never commit `.env` to source control.
- Use `uv` when you want faster dependency installation and environment setup.
- The bot uses an in-memory response cache for simple context preservation.
