<img src="./.github/assets/app-icon.png" alt="Voice Assistant App Icon" width="100" height="100">

# LiveKit Agent Bundle

This project is a comprehensive voice assistant solution built with [LiveKit Agents](https://docs.livekit.io/agents). It combines a Next.js frontend with Python-powered AI agents to create an interactive voice interface. The bundle supports [voice interactions](https://docs.livekit.io/agents/start/voice-ai), [transcriptions](https://docs.livekit.io/agents/build/text/), and [virtual avatars](https://docs.livekit.io/agents/integrations/avatar).

The frontend is built with Next.js, while the agent backend is powered by Python using the LiveKit Agents SDK. This project supports multiple AI providers including Azure OpenAI, Google AI, and Cerebras.

![App screenshot](/.github/assets/frontend-screenshot.jpeg)

## Project Structure

This project consists of two main components:

1. **Frontend** - A Next.js application that provides the user interface
2. **Agent** - Python scripts that power the AI voice assistant

### Frontend (Next.js)

The frontend is built with Next.js and uses the LiveKit JavaScript SDK to handle real-time communication.

### Agent (Python)

The agent directory contains multiple Python scripts for different AI providers:
- `default-azure.py` - Azure OpenAI-powered voice assistant
- `default-google.py` - Google AI-powered voice assistant
- `default-cerebras.py` - Cerebras-powered voice assistant
- Additional specialized agent implementations

## Getting Started

> [!TIP]
> If you'd like to try this application without modification, you can deploy an instance in just a few clicks with [LiveKit Cloud Sandbox](https://cloud.livekit.io/projects/p_/sandbox/templates/voice-assistant-frontend).

### Frontend Setup

Run the following command to automatically clone this template:

```bash
lk app create --template voice-assistant-frontend
```

Then run the frontend with:

```bash
pnpm install
pnpm dev
```

And open http://localhost:3000 in your browser.

### Python Agent Setup

1. Navigate to the agent directory:
   ```bash
   cd agent
   ```

2. Install the required Python packages:
   ```bash
   pip install livekit-agents python-dotenv
   ```

3. Configure your environment variables:
   ```bash
   cp env.example .env
   ```
   Edit the `.env` file with your API keys and configuration.

4. Run an agent (choose one based on your available API keys):
   ```bash
   python default-azure.py
   # or
   python default-google.py
   # or
   python default-cerebras.py
   ```

> [!NOTE]
> For the frontend, if you need to modify the LiveKit project credentials used, you can edit `.env.local` (copy from `.env.example` if you don't have one) to suit your needs.

## Deploying to Vercel

You can easily deploy the frontend of this application to Vercel:

1. Fork this repository to your GitHub account

2. Sign in to [Vercel](https://vercel.com) and create a new project

3. Import your forked repository

4. Configure the following environment variables in the Vercel project settings:
   ```
   LIVEKIT_API_KEY=your_api_key
   LIVEKIT_API_SECRET=your_api_secret
   LIVEKIT_URL=your_livekit_url
   ```

5. Deploy the project

> [!NOTE]
> The Python agent needs to be deployed separately on a server that can run Python applications. You can use services like Heroku, AWS, or Google Cloud to host your agent.

## Python Agent Requirements

The Python agents require:
- Python 3.8 or higher
- `livekit-agents` package
- `python-dotenv` for environment variable management
- API keys for the AI provider of your choice (Azure OpenAI, Google AI, or Cerebras)

## Contributing

This template is open source and we welcome contributions! Please open a PR or issue through GitHub, and don't forget to join us in the [LiveKit Community Slack](https://livekit.io/join-slack)!
