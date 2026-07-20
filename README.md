# UNITEEAI - AI Video Advertisement App

## Overview
UNITEEAI is an intelligent platform for generating professional video advertisements using AI. It leverages computer vision, natural language processing, and video synthesis to create compelling ads from text prompts.

## Features
- 🎬 **AI-Powered Video Generation** - Generate ads from text descriptions
- 🎨 **Smart Scene Composition** - Automatic scene layout and transitions
- 🎤 **Voice & Narration** - Text-to-speech with multiple voice options
- 🎵 **Music Integration** - Auto-select background music
- 📊 **Analytics Dashboard** - Track ad performance metrics
- 🔧 **Customization** - Fine-tune colors, fonts, duration, and effects

## Tech Stack
- **Frontend:** Next.js, React, Tailwind CSS
- **Backend:** Python FastAPI, Node.js Express
- **AI/ML:** OpenAI GPT, Stable Diffusion, Whisper, Video synthesis models
- **Database:** PostgreSQL, Redis
- **Video Processing:** FFmpeg, MoviePy
- **Deployment:** Docker, Kubernetes

## Project Structure
```
UNITEEAI/
├── frontend/           # Next.js React application
├── backend/            # FastAPI Python backend
├── services/           # Microservices (video-gen, audio, ml)
├── docs/              # Documentation
├── docker-compose.yml # Local development setup
└── README.md          # This file
```

## Getting Started
See [docs/SETUP.md](docs/SETUP.md) for detailed setup instructions.

## License
MIT
