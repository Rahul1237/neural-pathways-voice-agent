# 🧠 Neural Pathways — Multi-Agent Voice AI System

A real-time voice AI system simulating a psychology therapy center. Talk to an AI receptionist, get transferred to a neuroplasticity specialist, and get answers powered by a RAG pipeline built on real psychology books.

> 🎥 **[Watch Demo](https://youtu.be/weuoeGQg-Is)**

---

## 🏗️ Architecture

```
User (Voice) 
    ↓
LiveKit (Real-time Audio/Video)
    ↓
PersonalAgent (Receptionist)
    ↙              ↘
PsychologyAgent    MCPAgent
(Dr. Sarah Chen)   (Research)
    ↓
RAG Pipeline
(LangChain + Pinecone)
    ↓
Psychology Knowledge Base
(Kahneman, Doidge, etc.)
```

---

## ✨ Features

- 🎙️ Real-time voice conversation with AI agents
- 🤖 Multi-agent system with intelligent handoffs
- 🧬 RAG pipeline over real psychology books
- 📝 Live transcription
- 🔊 Background office ambience audio
- 🎧 Noise cancellation (BVC)
- 🌐 React frontend with dark/light theme

---

## 🤖 Agents

| Agent | Role |
|-------|------|
| **PersonalAgent** | Receptionist — greets users and routes to specialists |
| **PsychologyAgent** | Dr. Sarah Chen — neuroplasticity & cognitive therapy expert |
| **MCPAgent** | Research specialist — handles web search queries |

---

## ⚙️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Voice Pipeline | LiveKit Agents |
| Speech to Text | Deepgram STTv2 |
| Text to Speech | Deepgram TTS (aura-2-helena-en) |
| LLM | OpenAI GPT-4o-mini |
| RAG | LangChain + Pinecone |
| VAD | Silero VAD |
| Turn Detection | LiveKit EnglishModel |
| Frontend | React 19 + Vite |
| Backend | Python + uv |

---

## 🚀 Setup

### Prerequisites
- Node.js 18+
- Python 3.11+
- [uv](https://github.com/astral-sh/uv)
- LiveKit Cloud account
- Deepgram API key
- OpenAI API key
- Pinecone API key

### 1. Clone the repo
```bash
git clone https://github.com/Rahul1237/neural-pathways-voice-agent.git
cd neural-pathways-voice-agent
```

### 2. Frontend setup
```bash
cd agent-react
npm install
```

Create `.env` in `agent-react/`:
```env
VITE_LIVEKIT_URL=wss://your-project.livekit.cloud
VITE_LIVEKIT_API_KEY=your-api-key
VITE_LIVEKIT_API_SECRET=your-api-secret
```

### 3. Backend setup
```bash
cd backend
uv sync
uv run agent.py download-files
```

Create `.env` in `backend/`:
```env
LIVEKIT_URL=wss://your-project.livekit.cloud
LIVEKIT_API_KEY=your-api-key
LIVEKIT_API_SECRET=your-api-secret
OPENAI_API_KEY=your-openai-key
DEEPGRAM_API_KEY=your-deepgram-key
PINECONE_API_KEY=your-pinecone-key
```

---

## ▶️ Running the Project

```bash
# Terminal 1 - Frontend
cd agent-react
npm run dev

# Terminal 2 - Backend
cd backend
uv run agent.py dev
```

Open [http://localhost:3000](http://localhost:3000)

---

## 💬 Example Conversation

```
You:      "Hello"
Agent:    "Welcome to Neural Pathways! How can I help you today?"

You:      "I've been feeling anxious lately"
Agent:    "Let me connect you with Dr. Sarah Chen..."

Dr. Chen: "Hello, I'm Dr. Sarah Chen. Tell me what's been going on..."

You:      "How can I rewire my brain to reduce anxiety?"
Dr. Chen: "Great question. Based on Doidge's research on neuroplasticity..."
```

---

## 📁 Project Structure

```
neural-pathways-voice-agent/
├── agent-react/          # React frontend
│   ├── src/
│   │   ├── components/   # UI components
│   │   ├── hooks/        # Custom React hooks
│   │   └── lib/          # Utilities
│   └── .env              # Frontend env vars (never commit)
├── backend/
│   ├── agent.py          # Main agent file
│   ├── rag/              # RAG pipeline
│   │   └── documents.py  # Knowledge base query
│   └── .env              # Backend env vars (never commit)
├── .gitignore
└── README.md
```

---

## 🔗 Links

- [LiveKit Documentation](https://docs.livekit.io)
- [Deepgram Documentation](https://developers.deepgram.com)
- [LangChain Documentation](https://python.langchain.com)
- [Pinecone Documentation](https://docs.pinecone.io)

---

## 👤 Author

**Rahul Varma Cherukuri**  
[LinkedIn](https://linkedin.com/in/rahul-varma-2957b2254) · [GitHub](https://github.com/Rahul1237) · [YouTube](https://youtu.be/weuoeGQg-Is)

--

⭐ If you found this useful, give it a star!