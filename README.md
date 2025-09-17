# Shell AI

A smart command-line assistant that converts natural language requests into shell commands using Google's Gemini AI model.

## Overview

Shell AI is a Python-based tool that helps users generate shell commands from natural language descriptions. It uses Google's Gemini 2.0 Flash model to understand user requests and provide appropriate shell commands with explanations of the reasoning process.

## Features

- 🤖 **AI-powered command generation** using Google Gemini 2.0 Flash
- 🧠 **Transparent reasoning** - shows AI's thought process before providing commands
- 🔒 **Safety first** - asks for confirmation before executing commands
- 🌍 **Multilingual support** - responds in the same language as your request
- ⚡ **Simple CLI interface** - easy to use from any terminal

## Prerequisites

- Python 3.10 or higher
- Google AI API key (Gemini)

## Installation

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Bayashat/Shell-ai.git
   cd Shell-ai
   ```

2. **Install dependencies using uv (recommended):**
   ```bash
   uv sync
   ```

   Or using pip:
   ```bash
   pip install -e .
   ```

3. **Set up your Google AI API key:**
   
   Create a `.env` file in the project root:
   ```bash
   echo "GEMINI_KEY=your_api_key_here" > .env
   ```

   To get a Google AI API key:
   - Visit [Google AI Studio](https://aistudio.google.com/)
   - Sign in with your Google account
   - Create a new API key
   - Copy the key to your `.env` file

## Usage

After installation, you can use the `ai` command from anywhere in your terminal:

```bash
ai "list all files in the current directory"
```

```bash
ai "find all Python files modified in the last 7 days"
```

```bash
ai "create a backup of my home directory"
```

### Example Interaction

```bash
$ ai "show disk usage for the current directory"

(AI Thinking): The user wants to see disk usage for the current directory. 
The most appropriate command would be 'du' with options to show human-readable 
format and summary for the current directory.

(AI Answer): du -sh .
Execute? Y/N: y
4.2M    .
```


## Project Structure

```
shell-ai/
├── main.py          # Main application logic
├── pyproject.toml   # Project configuration and dependencies
├── uv.lock         # Dependency lock file
├── .env            # Environment variables (create this)
├── .gitignore      # Git ignore rules
└── README.md       # This file
```

## Configuration

The application uses the following environment variables:

- `GEMINI_KEY`: Your Google AI API key (required)

## Dependencies

- **pydantic-ai-slim[google]**: AI framework with Google provider support
- **python-dotenv**: Environment variable management

**Note**: Always review generated commands before execution, especially for system-critical operations.
