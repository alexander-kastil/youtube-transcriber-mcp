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

- Execute src\youtube-transcriber-mcp\start.ps1. This PowerShell script will create a virtual environment, install the required dependencies, and start the MCP server on `http://127.0.0.1:8000/mcp`.

> Note: There is also a start.sh script for Linux/macOS users.

- Run MCP Inspector using:

```bash
npx mcp-inspector --transport streamable-http --server-url http://127.0.0.1:8000/mcp
```
