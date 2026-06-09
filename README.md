# GitHub MCP Agent

An intelligent GitHub repository analysis tool powered by AI and the Model Context Protocol (MCP).

## 🎯 Features

- **Natural Language Queries**: Ask questions about GitHub repositories in plain English
- **Multiple Query Types**:
  - **Info**: Get comprehensive repository details from README
  - **Issues**: Find and analyze recent issues
  - **Pull Requests**: Review recent merged PRs
  - **Repository Activity**: Analyze code quality trends
  - **Custom**: Ask anything about the repository
- **AI-Powered Analysis**: Uses Nebius AI model for intelligent insights
- **Real-time Results**: Async processing with formatted markdown responses
- **Table Format**: Presents complex data in organized tables with links

## 📋 Prerequisites

Before running this application, ensure you have:

1. **Python 3.10+** installed
2. **Docker** installed and running
3. **Git** (optional, for cloning)
4. Two API keys:
   - Nebius API key (https://nebius.ai)
   - GitHub Personal Access Token (https://github.com/settings/tokens)

## 🚀 Installation

### 1. Clone the repository
```bash
git clone https://github.com/YOUR_USERNAME/github-mcp-agent.git
cd github-mcp-agent
```

### 2. Create a virtual environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Set up environment variables
```bash
# Copy the example file
copy .env.example .env  # Windows
cp .env.example .env    # macOS/Linux

# Edit .env and add your API keys
```

## 🔑 Getting API Keys

### GitHub Personal Access Token
1. Go to https://github.com/settings/tokens
2. Click "Generate new token"
3. Select scopes: `repo`, `read:user`, `public_repo`
4. Copy and paste in `.env` as `GITHUB_PERSONAL_ACCESS_TOKEN`

### Nebius API Key
1. Visit https://nebius.ai
2. Create an account or login
3. Generate an API key from dashboard
4. Copy and paste in `.env` as `NEBIUS_API_KEY`

## ▶️ Running the Application

```bash
# Make sure your virtual environment is activated
# and you're in the project directory

streamlit run main.py
```

The application will start at `http://localhost:8501`

## 📖 Usage

1. **Enter API Keys** in the sidebar (only needed once per session)
2. **Select Query Type** from the dropdown
3. **Enter Repository** in format: `owner/repo` (e.g., `Arindam200/awesome-ai-apps`)
4. **Modify Query** if needed (pre-filled based on query type)
5. **Click "Run Query"** to analyze the repository

## 📋 Example Queries

- "Tell me all about microsoft/vscode"
- "Find critical bugs in react repository"
- "Show recent security improvements in nodejs"
- "Analyze community engagement in tensorflow"

## 🔧 System Requirements

- **RAM**: 4GB minimum (8GB recommended)
- **Docker**: Required for GitHub MCP server
- **Disk Space**: ~2GB for dependencies

## 🐛 Troubleshooting

### "Logo file not found"
- Create an `assets` folder in the project root
- Add `agno.png` and `Nebius.png` files to it

### "Docker not running"
- Ensure Docker Desktop is running
- Check Docker installation: `docker --version`

### "Error creating client session"
- Verify GitHub token has correct scopes
- Check GITHUB_PERSONAL_ACCESS_TOKEN in `.env`

### "API Key error"
- Confirm NEBIUS_API_KEY is set in `.env`
- Check API key validity on Nebius dashboard

## 📁 Project Structure

```
github-mcp-agent/
├── main.py                 # Main Streamlit application
├── requirements.txt        # Python dependencies
├── Pyprojects.toml        # Project configuration
├── README.md              # This file
├── .env.example           # Environment variables template
├── .gitignore             # Git ignore rules
└── assets/                # Images and assets (create this folder)
    ├── agno.png
    └── Nebius.png
```

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License - see the LICENSE file for details.

## ⭐ Acknowledgments

- Built with [Streamlit](https://streamlit.io/)
- Powered by [Nebius AI](https://nebius.ai)
- Uses [Model Context Protocol (MCP)](https://modelcontextprotocol.io/)
- Agent framework by [Agno](https://agno.ai/)

## 📞 Support

For issues or questions:
- Open an [GitHub Issue](https://github.com/YOUR_USERNAME/github-mcp-agent/issues)
- Check existing documentation

## 🗺️ Roadmap

- [ ] Add support for GitLab
- [ ] Add local model support (Ollama)
- [ ] Add query result caching
- [ ] Add export to PDF/JSON
- [ ] Add batch repository analysis
- [ ] Add custom instructions per user
