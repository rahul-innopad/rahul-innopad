# GitHub Profile Visit Tracker API

## Base URL
The API is available at: `http://localhost:3001/api`

## Endpoints

### GET /api/profile/visits
Returns the total visit count and history.

**Response**
```json
{
  "visits": 42,
  "history": [
    {
      "timestamp": "2024-03-15T10:30:00Z",
      "userAgent": "Mozilla/5.0...",
      "referrer": "github.com",
      "ip": "127.0.0.1"
    }
  ]
}
```

### POST /api/profile/track
Tracks a new profile visit.

**Response**
```json
{
  "visits": 43,
  "message": "Visit tracked successfully"
}
```

### GET /api/profile/badge
Returns an SVG badge showing the visit count. Perfect for embedding in your GitHub profile README.

**Usage in GitHub Profile**
```markdown
![Profile Views](https://your-api-domain.com/api/profile/badge)
```

### GET /api/profile/analytics
Returns detailed analytics about profile visits.

**Response**
```json
{
  "totalVisits": 42,
  "dailyVisits": {
    "2024-03-15": 5,
    "2024-03-14": 3
  },
  "recentVisitors": [
    {
      "timestamp": "2024-03-15T10:30:00Z",
      "userAgent": "Mozilla/5.0...",
      "referrer": "github.com",
      "ip": "127.0.0.1"
    }
  ]
}
```

## How to Use with GitHub Profile

1. Deploy this API to a hosting service (e.g., Heroku, Vercel, or DigitalOcean)

2. Add this to your GitHub profile README.md:
   ```markdown
   ![Profile Views](https://your-api-domain.com/api/profile/badge)
   
   <!-- Optional: Add detailed analytics -->
   <details>
   <summary>📊 Profile Analytics</summary>
   
   <!-- Replace with your deployed frontend URL -->
   [View Analytics Dashboard](https://your-analytics-dashboard.com)
   </details>
   ```

3. The badge will automatically update as people visit your profile!

## Getting Started Locally
1. Install dependencies:
   ```bash
   npm install
   ```

2. Start the API server:
   ```bash
   npm run server
   ```

3. The API will be available at `http://localhost:3001/api`

## Security Considerations
- Consider adding rate limiting for production
- Add API key authentication for sensitive endpoints
- Implement IP address anonymization
- Regular cleanup of old visit data
