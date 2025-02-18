# Markdownify MCP Server

Markdownify is a Model Context Protocol (MCP) server that converts various file types and web content to Markdown format. It provides a set of tools to transform PDFs, images, audio files, web pages, and more into easily readable and shareable Markdown text.

<a href="https://glama.ai/mcp/servers/bn5q4b0ett"><img width="380" height="200" src="https://glama.ai/mcp/servers/bn5q4b0ett/badge" alt="Markdownify Server MCP server" /></a>

## Features
- Convert multiple file types to Markdown:
  - PDF
  - Images
  - Audio (with transcription)
  - DOCX
  - XLSX
  - PPTX
- Convert web content to Markdown:
  - YouTube video transcripts
  - Bing search results
  - General web pages
- Retrieve existing Markdown files

## Installation

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/pashpashpash/markdownify-mcp.git
   cd markdownify-mcp
   ```

2. **Install Dependencies**:
   ```bash
   pnpm install
   ```
   Note: This will also install `uv` and related Python dependencies.

3. **Build the Project**:
   ```bash
   pnpm run build
   ```

## Usage with Claude Desktop

Add the following to your claude_desktop_config.json:
- macOS: `~/Library/Application Support/Claude/claude_desktop_config.json`
- Windows: `%APPDATA%/Claude/claude_desktop_config.json`

```json
{
  "mcpServers": {
    "markdownify": {
      "command": "node",
      "args": ["path/to/markdownify-mcp/dist/index.js"],
      "env": {
        "UV_PATH": "/path/to/uv"
      }
    }
  }
}
```
Note: Replace "path/to/markdownify-mcp" with the actual path to your cloned repository.

## Available Tools

- `youtube-to-markdown`: Convert YouTube videos to Markdown
- `pdf-to-markdown`: Convert PDF files to Markdown
- `bing-search-to-markdown`: Convert Bing search results to Markdown
- `webpage-to-markdown`: Convert web pages to Markdown
- `image-to-markdown`: Convert images to Markdown with metadata
- `audio-to-markdown`: Convert audio files to Markdown with transcription
- `docx-to-markdown`: Convert DOCX files to Markdown
- `xlsx-to-markdown`: Convert XLSX files to Markdown
- `pptx-to-markdown`: Convert PPTX files to Markdown
- `get-markdown-file`: Retrieve an existing Markdown file

## Development

```bash
# Start TypeScript compiler in watch mode
pnpm run dev

# Build the project
pnpm run build
```

### Server Customization
- Modify `src/server.ts` to customize server behavior
- Add or modify tools in `src/tools.ts`

### Debugging

If you run into issues, check Claude Desktop's MCP logs:
```bash
tail -n 20 -f ~/Library/Logs/Claude/mcp*.log
```

## Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
Note: This is a fork of the [original markdownify-mcp repository](https://github.com/zcaceres/markdownify-mcp).
