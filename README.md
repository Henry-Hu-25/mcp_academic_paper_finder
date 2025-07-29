# MCP Standard I/O Deployment

- Initialize the project
    - `uv init`
- Create virtual environment and activate it:
    - `uv venv`
    - `source .venv/bin/activate`
- Install dependencies:
    - `uv add mcp arxiv anthropic nest-asyncio`
- Launch the inspector (Optional):
    - `npx @modelcontextprotocol/inspector uv run research_server.py`
- Run the client:
    - `uv run mcp_chatbot.py`

# MCP SSE Deployment

## MCP Inspector

- Initialize the project
    - `uv init`
- Create virtual environment and activate it:
    - `uv venv`
    - `source .venv/bin/activate`
- Install dependencies:
    - `uv add mcp arxiv anthropic nest-asyncio python-dotenv`
- Run the server:
    - `uv run research_server.py`
    - Notice the url of the server
- Launch the inspector:
    - `npx @modelcontextprotocol/inspector`
    - Change Transport Type to SSE
    - Add the url of the server to the URL field

## Render Deployment

### Prerequisites
- Render account (free tier available)
- GitHub repository with your MCP server

### Prepare Your Project for Deployment

1. Ensure Render compatability
    - Create a `requirements.txt` file in your project root:
        - `uv pip compile pyproject.toml > requirements.txt`
        - render works with pip
    - Make sure Render uses the right version of python
        - `echo "python-version: 3.11" > runtime.txt`

2. Deploy necessary files to GitHub

3. Deploy as a web service on render
    - Create an account on render.com
    - Link the GitHub repo
    - Start Command: `python research_server.py`
