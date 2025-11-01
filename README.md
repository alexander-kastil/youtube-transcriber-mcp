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

1. Navigate to the `src` directory:
   ```bash
   cd src
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run the server:
   ```bash
   python server.py
   ```

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
