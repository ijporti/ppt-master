# PPT Master

A powerful AI-powered presentation generator that creates beautiful PowerPoint files from text prompts.

> Fork of [hugohe3/ppt-master](https://github.com/hugohe3/ppt-master) with additional features and improvements.

## Features

- 🤖 AI-driven slide content generation (OpenAI / compatible APIs)
- 🎨 Multiple built-in themes and layouts
- 📊 Auto-generated charts and diagrams
- 📝 Markdown-to-PPTX conversion
- 🌐 Web UI for easy interaction
- 🔌 REST API for programmatic access

## Quick Start

### Prerequisites

- Python 3.10+
- An OpenAI-compatible API key

### Installation

```bash
# Clone the repository
git clone https://github.com/your-username/ppt-master.git
cd ppt-master

# Create and activate a virtual environment
python -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Copy and configure environment variables
cp .env.example .env
# Edit .env with your API keys and settings
```

### Running the App

```bash
python app.py
```

Then open your browser at `http://localhost:7860`.

## Configuration

All configuration is done via the `.env` file. See [`.env.example`](.env.example) for a full list of available options.

| Variable | Description | Default |
|---|---|---|
| `OPENAI_API_KEY` | Your OpenAI (or compatible) API key | *(required)* |
| `OPENAI_API_BASE` | Base URL for the API endpoint | `https://api.openai.com/v1` |
| `MODEL_NAME` | LLM model to use for generation | `gpt-4o` |
| `MAX_SLIDES` | Maximum number of slides per presentation | `20` |
| `THEME` | Default presentation theme | `default` |

## Project Structure

```
ppt-master/
├── app.py              # Main entry point (Gradio web UI)
├── api.py              # FastAPI REST endpoints
├── core/
│   ├── generator.py    # Slide content generation logic
│   ├── builder.py      # PPTX file builder
│   └── themes.py       # Theme definitions
├── utils/
│   ├── llm.py          # LLM client wrapper
│   └── helpers.py      # Shared utility functions
├── templates/          # PPTX template files
├── static/             # Static assets for the web UI
├── tests/              # Unit and integration tests
├── .env.example        # Environment variable reference
└── requirements.txt    # Python dependencies
```

## API Usage

```bash
curl -X POST http://localhost:7860/api/generate \
  -H "Content-Type: application/json" \
  -d '{"prompt": "Introduction to Machine Learning", "slides": 10}'
```

## Contributing

Contributions are welcome! Please open an issue or submit a pull request.

1. Fork the repository
2. Create a feature branch (`git checkout -b feat/my-feature`)
3. Commit your changes (`git commit -m 'feat: add my feature'`)
4. Push to the branch (`git push origin feat/my-feature`)
5. Open a Pull Request

## License

MIT License — see [LICENSE](LICENSE) for details.
