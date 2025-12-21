# 3D AI Chatbot

Enterprise-grade 3D AI chatbot with voice interaction, realistic lip sync, and an animated ReadyPlayer.me avatar.

![Demo](https://models.readyplayer.me/69427bcc403c0000633446b9.png)

## Features

- 🤖 **AI-Powered Chat** - Groq LLM (Mixtral) for intelligent responses
- 🎤 **Text-to-Speech** - ElevenLabs for natural voice
- 👄 **Lip Sync** - Rhubarb for realistic mouth animation
- 🎭 **3D Avatar** - ReadyPlayer.me avatar with morph targets
- ⚡ **Real-time** - FastAPI backend with async processing

## Tech Stack

| Layer | Technology |
|-------|------------|
| Frontend | React, Three.js, @react-three/fiber |
| Backend | Python FastAPI |
| LLM | Groq API (Mixtral) |
| Voice | ElevenLabs TTS |
| Lip Sync | Rhubarb Lip Sync |
| Avatar | ReadyPlayer.me GLB |

## Quick Start

### Prerequisites

- Python 3.8+
- Node.js 18+
- [Rhubarb Lip Sync](https://github.com/DanielSWolf/rhubarb-lip-sync/releases)
- API Keys: [Groq](https://console.groq.com/), [ElevenLabs](https://elevenlabs.io/)

### 1. Setup Backend

```bash
cd Backend

# Create virtual environment
python -m venv venv
venv\Scripts\activate  # Windows
# source venv/bin/activate  # Mac/Linux

# Install dependencies
pip install -r requirements.txt

# Configure environment
copy .env.example .env
# Edit .env with your API keys

# Run server
uvicorn app.main:app --reload
```

### 2. Setup Frontend

```bash
cd frontend

# Install dependencies
npm install

# Run development server
npm run dev
```

### 3. Open Application

Navigate to `http://localhost:5173`

## Configuration

### Backend `.env`

```env
GROQ_API_KEY=your_groq_api_key
ELEVENLABS_API_KEY=your_elevenlabs_api_key
ELEVENLABS_VOICE_ID=21m00Tcm4TlvDq8ikWAM
RHUBARB_EXE_PATH=C:/path/to/rhubarb.exe
```

## API Endpoints

| Method | Endpoint | Description |
|--------|----------|-------------|
| GET | `/health` | Health check |
| POST | `/api/chat` | Send message, get response with audio & lip sync |
| POST | `/api/chat/reset` | Reset conversation history |
| GET | `/api/audio/{filename}` | Get audio file |

## Project Structure

```
3D-Chatbot/
├── Backend/
│   ├── app/
│   │   ├── main.py           # FastAPI app
│   │   ├── config.py         # Settings
│   │   ├── routes/           # API endpoints
│   │   └── services/         # Business logic
│   ├── requirements.txt
│   └── .env.example
├── frontend/
│   ├── src/
│   │   ├── App.jsx           # Main component
│   │   ├── components/       # React components
│   │   ├── services/         # API client
│   │   └── index.css         # Styles
│   └── package.json
└── README.md
```

## License

MIT
