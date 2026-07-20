# System Architecture

## Overview
UNITEEAI follows a microservices architecture with clear separation between frontend, API layer, and specialized services.

```
┌──────────────────────────────────────┐
│   React Frontend    │
│   (Next.js)         │
└──────────────────────────────────┬───┘
           │ HTTP/REST
           ▼
┌──────────────────────────────────────┐
│  API Gateway        │
│  (FastAPI)          │
└──────────────────────────────────┬───┘
           │
      ┌────┴────┬────────┬──────────────┬──────────────┐
      ▼         ▼        ▼              ▼              ▼
┌──────────┐ ┌──────────┐ ┌──────────┐ ┌──────────┐
│ Video    │ │ Audio    │ │ Text     │ │ Image    │
│ Service  │ │Service   │ │Service   │ │Service   │
└────┬─────┘ └────┬─────┘ └────┬─────┘ └────┬─────┘
     │            │            │            │
     └────┬───────┴────────────┴────────────┘
          ▼
  ┌──────────────────────────────────────┐
  │ PostgreSQL DB    │
  │ Redis Cache      │
  └──────────────────────────────────────┘
```

## Components

### Frontend
- **Technology:** Next.js 14, React 18, Tailwind CSS
- **State Management:** Zustand
- **Features:**
  - Ad template selection
  - Text/script input interface
  - Video preview and editor
  - Analytics dashboard

### API Gateway (FastAPI)
- Central request handler
- Authentication/Authorization
- Request validation
- Response formatting
- Rate limiting

### Microservices

#### Video Generation Service
- Text-to-video synthesis
- Scene composition
- Transitions and effects
- Output encoding

#### Audio Service
- Text-to-speech (TTS)
- Voice selection
- Audio mixing
- Music integration

#### Text Processing Service
- Script generation (GPT)
- Sentiment analysis
- SEO optimization

#### Image Service
- Image generation (Stable Diffusion)
- Image editing/composition
- Asset management

## Data Flow

1. User submits ad brief (text, industry, target audience)
2. Text Service generates script using GPT
3. Image Service creates visual assets
4. Audio Service generates voiceover
5. Video Service composes final video
6. Output stored in S3/storage
7. Results sent to frontend

## Database Schema
- **Users:** Authentication & profiles
- **Projects:** Ad campaigns
- **Videos:** Generated video metadata
- **Assets:** Images, audio files
- **Templates:** Pre-built ad templates

## Security
- JWT authentication
- Rate limiting
- Input validation (Pydantic)
- CORS enabled
- Environment variable management
