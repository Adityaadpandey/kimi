# KIMI 🤖

> Your real-time AI assistant for productivity and daily management

[![n8n](https://img.shields.io/badge/Built%20with-n8n-FF6D5A)](https://n8n.io/)
[![PostgreSQL](https://img.shields.io/badge/Database-PostgreSQL-336791)](https://www.postgresql.org/)
[![OpenAI](https://img.shields.io/badge/Powered%20by-OpenAI-412991)](https://openai.com/)

KIMI is a personal AI assistant that acts as your virtual manager, helping you stay productive throughout the day. Built on n8n's multi-agent workflow system, KIMI provides real-time conversational assistance, automated morning briefings, and nightly task summaries—all through Telegram.

## ✨ Features

- **🗣️ Real-Time Conversational AI** - Natural, human-like interactions via Telegram with a warm, direct communication style
- **☀️ Automated Morning Briefings** - Daily calendar overview delivered at 8:30 AM to kickstart your day
- **🌙 Nightly Task Summaries** - Review of completed tasks and pending items at 10:30 PM for accountability
- **📅 Google Calendar Integration** - Seamless access to your daily schedule and events
- **✅ Todoist Integration** - Track task completion and manage your to-do list
- **⚡ Fast & Deployable** - Self-hosted solution with Docker for quick deployment
- **🔧 Multi-Agent Architecture** - Leverages n8n's workflow automation for complex task handling

## 🛠️ Installation

### Prerequisites

- Docker and Docker Compose
- Telegram Bot Token
- Google Calendar API credentials
- Todoist API credentials

### Quick Start

1. **Clone the repository**

   ```bash
   git clone https://github.com/Adityaadpandey/kimi.git
   cd kimi
   ```

2. **Configure environment variables**

   Create a `.env` file with the following:

   ```env
   POSTGRES_USER=your_postgres_user
   POSTGRES_PASSWORD=your_postgres_password
   POSTGRES_DB=n8n
   N8N_BASIC_AUTH_USER=your_n8n_user
   N8N_BASIC_AUTH_PASSWORD=your_n8n_password
   ```

3. **Start the services**

   ```bash
   docker-compose up -d
   ```

4. **Access n8n**

   Navigate to your n8n instance and import the workflow files:
   - `kimi.json` - Main conversational workflow
   - `kimi-morning.json` - Morning briefing workflow
   - `kimi-night.json` - Nightly summary workflow

## 📖 Usage

Once deployed, KIMI operates automatically through three main workflows:

### Conversational Assistant

Simply message your Telegram bot to interact with KIMI. The assistant will:

- Respond concisely (1-2 lines)
- Execute tools silently without over-explaining
- Maintain a warm, direct communication style

### Automated Schedules

| Schedule | Time | Action |
|----------|------|--------|
| Morning Briefing | 8:30 AM | Fetches and summarizes today's calendar events |
| Nightly Summary | 10:30 PM | Reviews completed and pending Todoist tasks |

## ⚙️ Configuration

### Workflow Files

| File | Purpose |
|------|---------|
| `kimi.json` | Main AI agent with custom persona and tool integrations |
| `kimi-morning.json` | Scheduled morning calendar briefing |
| `kimi-night.json` | Scheduled nightly task review |
| `docker-compose.yaml` | Infrastructure setup (PostgreSQL + n8n) |

### Required Integrations

Configure these credentials in your n8n instance:

- **Telegram Bot** - For message sending/receiving
- **Google Calendar OAuth2** - For calendar access
- **Todoist OAuth2** - For task management

### Infrastructure

The `docker-compose.yaml` includes:

- PostgreSQL database for workflow persistence
- n8n instance with HTTPS/webhook support
- Basic auth protection for the n8n editor
- Nginx proxy configuration ready

## 🏗️ Architecture

![Architecture]('image.png')

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is open source. See the repository for license details.

---

<p align="center">
  Made with ❤️ by <a href="https://github.com/Adityaadpandey">Aditya</a>
</p>
