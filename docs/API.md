# API Documentation

## Base URL
```
http://localhost:8000
```

## Authentication
All protected endpoints require JWT token in header:
```
Authorization: Bearer <token>
```

## Endpoints

### Health Check
```http
GET /health
```

### Generate Video Advertisement
```http
POST /api/v1/videos/generate
Content-Type: application/json

{
  "brief": "Create a 30-second ad for a coffee shop",
  "industry": "Food & Beverage",
  "target_audience": "Young professionals",
  "tone": "Professional",
  "duration": 30,
  "resolution": "1080p"
}

Response: 201 Created
{
  "video_id": "uuid",
  "status": "processing",
  "progress": 0,
  "created_at": "2024-01-15T10:30:00Z"
}
```

### Get Video Status
```http
GET /api/v1/videos/{video_id}

Response: 200 OK
{
  "video_id": "uuid",
  "status": "completed",
  "progress": 100,
  "video_url": "https://s3.../video.mp4",
  "thumbnail": "https://s3.../thumbnail.jpg",
  "duration": 30,
  "created_at": "2024-01-15T10:30:00Z",
  "completed_at": "2024-01-15T10:35:00Z"
}
```

### List Videos
```http
GET /api/v1/videos?limit=10&offset=0

Response: 200 OK
{
  "total": 42,
  "videos": [...]
}
```

### Download Video
```http
GET /api/v1/videos/{video_id}/download

Response: 200 OK (video file)
```

## Error Handling

```json
{
  "detail": "Error message",
  "error_code": "ERROR_TYPE",
  "timestamp": "2024-01-15T10:30:00Z"
}
```

## Rate Limiting
- 100 requests per minute per user
- 10 concurrent video generations
