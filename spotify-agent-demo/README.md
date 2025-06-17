# 🎵 Spotify AI Agent Demo

A Next.js web interface for the **Spotify Music Agent** with clean architecture and LangSmith tracing.

## 🚀 Features

- **Clean UI**: Modern React interface with Tailwind CSS
- **Real-time Chat**: Direct communication with the SpotifyMusicAgent
- **Song Cards**: Beautiful display of music recommendations
- **Tool Tracking**: See which tools the agent used for each response
- **Server Status**: Live connection monitoring
- **Brief DJ Responses**: Following Spotify's AI DJ style

## 🛠️ Architecture

This demo connects to the clean **SpotifyMusicAgent** backend:
- **Backend**: `agent/simple_api.py` - FastAPI server with SpotifyMusicAgent
- **Frontend**: Next.js React app with TypeScript
- **Communication**: REST API with structured JSON responses

## 📋 Prerequisites

1. **Backend Server**: Make sure the SpotifyMusicAgent API is running
   ```bash
   # From the root directory
   python run_api.py
   ```

2. **Environment Variables**: Ensure your `.env` file has:
   ```env
   OPENAI_API_KEY=your_openai_key
   SPOTIFY_CLIENT_ID=your_spotify_client_id
   SPOTIFY_CLIENT_SECRET=your_spotify_client_secret
   TAVILY_API_KEY=your_tavily_key
   ```

## 🏃‍♂️ Getting Started

1. **Install Dependencies**:
   ```bash
   npm install
   # or
   yarn install
   ```

2. **Start the Development Server**:
   ```bash
   npm run dev
   # or
   yarn dev
   ```

3. **Open in Browser**:
   Navigate to [http://localhost:3000](http://localhost:3000)

## 🎯 Usage

1. **Check Connection**: Ensure the green "Connected" status in the header
2. **Ask for Music**: Try queries like:
   - "Find me some Taylor Swift songs"
   - "Create a workout playlist"
   - "What are some good jazz tracks?"
   - "Who won the Grammy for Best New Artist in 2024?"

3. **View Results**:
   - Brief DJ responses (1-2 sentences)
   - Song cards with album art and Spotify links
   - Tool usage indicators

## 🔧 API Integration

The frontend communicates with the SpotifyMusicAgent through these endpoints:

- `GET /health` - Server status check
- `POST /chat` - Send music queries
  ```json
  {
    "query": "Find me some pop songs"
  }
  ```

Response structure:
```json
{
  "response": "Here are some great pop hits!",
  "unique_tools_used": ["search_tracks"],
  "songs_found": 10,
  "success": true
}
```

## 🎵 What Makes This Special

- **LangSmith Tracing**: All agent interactions traced for observability
- **Brief Responses**: Matches Spotify DJ personality (1-2 sentences max)
- **Multi-Tool Strategy**: Agent uses multiple tools strategically
- **Structured Data**: Clean Pydantic models for reliable parsing
- **Modern UI**: Responsive design with smooth animations

## 🔍 Troubleshooting

- **"Offline" Status**: Make sure `python run_api.py` is running
- **No Songs Displayed**: Check browser console for API errors
- **Slow Responses**: Agent may be using multiple tools (normal)

## 🏗️ Development

- **Frontend**: Built with Next.js 14, TypeScript, Tailwind CSS
- **Components**: Reusable UI components in `/components`
- **API Layer**: Clean separation in `/lib`
- **Styling**: Spotify-inspired green theme

Built to showcase the clean SpotifyMusicAgent architecture with LangSmith tracing! 🎧
