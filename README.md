# Multi AI Agent System

A production-ready AI agent application that combines multiple LLM models with web search capabilities, built with modern Python frameworks and deployed on AWS.

## What It Does

This project lets you interact with powerful AI models (Llama 3) through a clean web interface. You can ask questions, enable web search for real-time information, and customize the agent's behavior with system prompts. Think of it as your personal AI assistant that can search the web when needed.

## Tech Stack

- **Backend**: FastAPI for the REST API
- **Frontend**: Streamlit for the UI
- **AI Models**: Groq's Llama models (70B variants)
- **Agent Framework**: LangGraph with ReAct pattern
- **Web Search**: Tavily API integration
- **DevOps**: Jenkins CI/CD, Docker, SonarQube, AWS ECS Fargate

## Features

- 🤖 Multiple AI model selection (Llama 3 70B, Llama 3.3 70B)
- 🔍 Optional web search powered by Tavily
- 💬 Custom system prompts for agent behavior
- 📝 Comprehensive logging system
- 🚀 Containerized deployment
- 🔄 Automated CI/CD pipeline
- ☁️ AWS ECS Fargate hosting

## Quick Start

1. **Clone the repository**
```bash
git clone https://github.com/sanjay-suthraye/MULTI-AI-AGENT-PROJECTS.git
cd MULTI-AI-AGENT-PROJECTS
```

2. **Set up environment variables**
Create a `.env` file with:
```
GROQ_API_KEY=your_groq_api_key
TAVILY_API_KEY=your_tavily_api_key
```

3. **Install dependencies**
```bash
pip install -e .
```

4. **Run the application**
```bash
python app/main.py
```

The frontend will be available at `http://localhost:8501` and the backend API at `http://localhost:9999`.

## Docker Deployment

```bash
docker build -t multi-ai-agent .
docker run -p 8501:8501 -p 9999:9999 --env-file .env multi-ai-agent
```

## Architecture

The application follows a clean architecture pattern:
- **Frontend**: Streamlit UI for user interactions
- **Backend**: FastAPI REST API handling requests
- **Core**: AI agent logic using LangGraph
- **Common**: Shared utilities (logging, exceptions)
- **Config**: Environment and settings management

## CI/CD Pipeline

Automated pipeline using Jenkins:
1. Code checkout from GitHub
2. SonarQube analysis for code quality
3. Docker image build and push to AWS ECR
4. Deployment to AWS ECS Fargate

## API Endpoints

### POST `/chat`
Send queries to the AI agent.

**Request body:**
```json
{
  "model_name": "llama3-70b-8192",
  "system_prompt": "You are a helpful assistant",
  "messages": ["What is machine learning?"],
  "allow_search": true
}
```

## Project Structure

```
├── app/
│   ├── backend/        # FastAPI application
│   ├── frontend/       # Streamlit UI
│   ├── core/          # AI agent logic
│   ├── config/        # Settings & configuration
│   └── common/        # Shared utilities
├── custom_jenkins/    # Jenkins Docker setup
├── Dockerfile         # Main application container
├── Jenkinsfile        # CI/CD pipeline
└── requirements.txt   # Python dependencies
```


## License

This project is open source and available for educational purposes.

---

*Feel free to fork, star, or contribute to this project!*
