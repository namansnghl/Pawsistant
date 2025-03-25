# RAG Chatbot for Northeastern OGS
UniQbot is an AI-powered chatbot designed to enhance document Q&A capabilities for Northeastern University's Office of Global Services (OGS). The system leverages Retrieval-Augmented Generation (RAG) to provide instant, reliable answers to student queries, reducing dependency on office hours and improving overall accessibility to OGS services.

## Overview
UniQbot addresses the challenge of accessing timely information from the OGS due to high demand and limited office hours. By integrating web scraping, sophisticated preprocessing, and advanced language models, the chatbot provides accurate, contextually-aware responses to international student queries about immigration procedures, visa guidelines, and university policies.

## Features
- 💬 Natural language understanding and generation
- 🔍 Advanced retrieval system using FAISS vector database for efficient semantic search
- 📚 Knowledge base built from OGS website content with hybrid chunking strategies
- 🤖 Integration with Claude and GPT-3.5 language models for high-quality responses
- 📊 Superior performance metrics with Claude outperforming GPT-3.5 in accuracy and coherence
- 🌐 User-friendly web interface for real-time interaction
- 📋 Proper citation of information sources in responses
- 🔄 Response optimization through prompt engineering

## Installation

### Prerequisites
- Python 3.9 or higher
- PyTorch
- FAISS (Facebook AI Similarity Search)
- Hugging Face Transformers
- Flask for API deployment
- An API key for Claude or OpenAI (for GPT-3.5)

### Basic Installation
1. Clone the repository:
```bash
git clone https://github.com/namansnghl/UniQbot-rag.git
cd UniQbot-rag
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

3. Install required packages:
```bash
pip install -r requirements.txt
```

4. Set up environment variables for API keys:
```bash
# For Linux/Mac
export CLAUDE_API_KEY="your_claude_api_key"
export OPENAI_API_KEY="your_openai_api_key"

# For Windows
set CLAUDE_API_KEY="your_claude_api_key"
set OPENAI_API_KEY="your_openai_api_key"
```

## Usage

### Quick Start
1. Run the data preprocessing pipeline to build the knowledge base:
```bash
python scripts/preprocess.py
```

2. Launch the chatbot interface:
```bash
python app.py
```

3. Access the web interface at http://localhost:5000

### Advanced Configuration
- Modify `config.py` to adjust:
  - Chunk size and overlap percentage
  - Selection of embedding model
  - Number of retrieved documents (k)
  - Temperature settings for response generation
  - Choice of language model (Claude or GPT-3.5)

## UI Examples
The web interface provides a clean, intuitive chat experience where users can:
- Ask questions in natural language
- Receive detailed responses with citations
- View the confidence level of responses
- Access the source information when needed

## API Reference
UniQbot provides a RESTful API for integration with other systems:

```
POST /api/query
{
  "query": "What are the requirements for CPT?",
  "model": "claude",  // or "gpt"
  "max_tokens": 500
}
```

Response format:
```
{
  "answer": "CPT (Curricular Practical Training) requirements include...",
  "sources": ["https://international.northeastern.edu/ogs/..."],
  "confidence": 0.92
}
```

## Model Training
The UniQbot RAG system doesn't require traditional training but benefits from:
- Optimized embedding selection
- Refined chunking strategies
- Prompt engineering for the language models
- Performance tuning of retrieval parameters

Our evaluations show that Claude consistently outperforms GPT-3.5 in factual accuracy and coherence for this specific use case.

## Contributing
We welcome contributions to improve UniQbot:

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/amazing-feature`
3. Commit your changes: `git commit -m 'Add amazing feature'`
4. Push to the branch: `git push origin feature/amazing-feature`
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements
- Northeastern University Office of Global Services for providing the information domain
- The PyTorch, FAISS, and Hugging Face teams for their excellent libraries
- Anthropic (Claude) and OpenAI (GPT-3.5) for their language models

## {UNDER WORK}
