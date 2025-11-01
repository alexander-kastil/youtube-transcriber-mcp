# YouTube Transcription MCP Server

A Model Context Protocol (MCP) server that provides YouTube video transcription capabilities using the FastMCP framework.

## Features

- Extract video IDs from YouTube URLs (both youtube.com and youtu.be formats)
- Fetch video transcriptions using the YouTube Transcript API
- Support for multiple languages
- Built with FastMCP for easy integration with MCP clients

## Installation

1. Install the required dependencies:

```bash
pip install -r requirements.txt
```

## Usage

### Running the MCP Server Locally

To run the server locally:

```bash
python server.py
```

The server will start and listen for MCP protocol connections.

### Available Tools

#### `get_youtube_transcription`

Fetches the transcription of a YouTube video.

**Parameters:**
- `url` (required): The YouTube video URL (e.g., `https://www.youtube.com/watch?v=VIDEO_ID` or `https://youtu.be/VIDEO_ID`)
- `language` (optional): The language code for the transcript (default: "en"). Examples: "en" for English, "es" for Spanish, "fr" for French, etc.

**Returns:**
- The full transcription text of the video

**Example Usage:**
```python
# Using the MCP tool
result = get_youtube_transcription(
    url="https://www.youtube.com/watch?v=dQw4w9WgXcQ",
    language="en"
)
```

## Deployment to Azure App Service

### Prerequisites

- Azure CLI installed and configured
- Azure subscription
- Resource group created in Azure

### Deployment Steps

1. **Create an Azure App Service Plan:**

```bash
az appservice plan create \
    --name youtube-transcriber-plan \
    --resource-group <your-resource-group> \
    --sku B1 \
    --is-linux
```

2. **Create the Web App:**

```bash
az webapp create \
    --resource-group <your-resource-group> \
    --plan youtube-transcriber-plan \
    --name <your-app-name> \
    --runtime "PYTHON:3.12"
```

3. **Configure the startup command:**

```bash
az webapp config set \
    --resource-group <your-resource-group> \
    --name <your-app-name> \
    --startup-file "python server.py"
```

4. **Deploy the code:**

```bash
# From the src directory
az webapp up \
    --resource-group <your-resource-group> \
    --name <your-app-name> \
    --runtime "PYTHON:3.12"
```

5. **Configure environment variables (if needed):**

```bash
az webapp config appsettings set \
    --resource-group <your-resource-group> \
    --name <your-app-name> \
    --settings SETTING_NAME=value
```

### Alternative: Deploy using ZIP

```bash
# Create a ZIP file of the src directory
cd src
zip -r ../deploy.zip .

# Deploy the ZIP file
az webapp deployment source config-zip \
    --resource-group <your-resource-group> \
    --name <your-app-name> \
    --src ../deploy.zip
```

## Configuration

The server uses FastMCP which handles the MCP protocol communication. No additional configuration is required for basic usage.

## Error Handling

The server includes comprehensive error handling for:
- Invalid YouTube URLs
- Missing transcripts
- Network errors
- General transcription failures

All errors are logged and returned with descriptive messages.

## Dependencies

See `requirements.txt` for the complete list of dependencies:
- `azure-functions`: Azure Functions support
- `langchain`: LangChain framework
- `langchain-community`: Community integrations for LangChain
- `youtube-transcript-api`: YouTube transcript fetching
- `openai`: OpenAI API client
- `requests`: HTTP library
- `fastmcp`: FastMCP framework for MCP servers

## License

[Add your license information here]

## Contributing

[Add contribution guidelines here]
