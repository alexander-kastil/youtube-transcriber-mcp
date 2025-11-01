# YouTube Transcription MCP Server

A Model Context Protocol (MCP) server that provides YouTube video transcription capabilities using the FastMCP framework.

## Overview

This project implements an MCP server that allows AI assistants and other MCP clients to fetch transcripts from YouTube videos. It uses the YouTube Transcript API through LangChain's community integrations.

## Project Structure

```
.
├── README.md           # This file
├── .gitignore         # Git ignore configuration
└── src/               # Source code directory
    ├── __init__.py    # Package initialization
    ├── server.py      # Main MCP server implementation
    ├── requirements.txt # Python dependencies
    └── README.md      # Detailed documentation
```

## Features

- **Video ID Extraction**: Automatically extracts video IDs from YouTube URLs (supports both youtube.com and youtu.be formats)
- **Multi-language Support**: Fetch transcripts in different languages
- **FastMCP Integration**: Built on the FastMCP framework for seamless MCP protocol integration
- **Error Handling**: Comprehensive error handling with descriptive messages
- **Azure App Service Ready**: Includes deployment instructions for Azure App Service

## Quick Start

### 1. Create a Virtual Environment

It's recommended to use a virtual environment to isolate dependencies:

```bash
# Create a virtual environment
python -m venv venv

# Activate the virtual environment
# On Linux/macOS:
source venv/bin/activate
# On Windows:
# venv\Scripts\activate
```

### 2. Navigate to the `src/youtube-transcriber-mcp` directory:
   ```bash
   cd src/youtube-transcriber-mcp
   ```

### 3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

### 4. Run the server:
   ```bash
   python server.py
   ```

The server now runs with **Streamable HTTP transport by default**, making it compatible with modern MCP clients and testing tools.

## Testing with MCP Inspector

The [MCP Inspector](https://github.com/modelcontextprotocol/inspector) is a developer tool for testing MCP servers. To test this server with the inspector:

### Installation

```bash
# Install the MCP Inspector globally
npm install -g @modelcontextprotocol/inspector
```

### Running the Inspector

From the repository root directory, run:

```bash
# Start the inspector with your server
mcp-inspector python src/youtube-transcriber-mcp/server.py
```

This will:
1. Start your MCP server with Streamable HTTP transport
2. Open a web interface in your browser for testing
3. Allow you to interact with the `get_youtube_transcription` tool

### Testing the Tool

In the Inspector UI:
1. Navigate to the **Tools** section
2. Select the `get_youtube_transcription` tool
3. Provide test parameters:
   - `url`: A YouTube video URL (e.g., `https://www.youtube.com/watch?v=dQw4w9WgXcQ`)
   - `language`: Language code (e.g., `en` for English)
4. Click **Execute** to test the tool

The Inspector provides real-time feedback on requests, responses, and any errors.

## Documentation

For detailed documentation including:
- Tool usage examples
- Azure deployment instructions
- Configuration options

Please see [src/README.md](src/README.md)

## Dependencies

- `langchain`: LangChain framework
- `langchain-community`: Community integrations for LangChain
- `youtube-transcript-api`: YouTube transcript fetching
- `requests`: HTTP library
- `fastmcp`: FastMCP framework for MCP servers

## License

[Add your license information here]

## Contributing

[Add contribution guidelines here]
