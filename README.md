# WebMCP Agent Bridge

![Chat screenshot](./Chat-shot.png)

A lightweight browser-based chat app that connects model APIs to simple WebMCP tools exposed by the page.

## Features

- OpenAI-compatible, Ollama, and Anthropic provider adapters
- Custom endpoint and model support
- WebMCP tool registration for browser actions
- Counter demo tools to increment or decrement a value
- Voice input support in supported browsers
- Model selector loaded from the local Ollama API

## Requirements

- A browser with WebMCP support for tool registration
- A model endpoint that allows browser requests, or a local CORS-enabled proxy
- An API key for hosted providers; keys are kept in page memory only

## Run the app

From the project folder, serve it locally with:

```bash
npx serve .
```

Then visit:

```text
http://localhost:3000
```

## Provider presets

- **OpenAI-compatible**: works with OpenAI and compatible APIs such as local gateways. Set the endpoint, model, and key as needed.
- **Ollama**: defaults to `http://localhost:11434/api/chat` and `qwen3:4b`.
- **Anthropic**: defaults to `/v1/messages` and uses Anthropic's native tool format.

The app keeps an OpenAI-style conversation internally, then converts tools, messages, and tool results to the selected provider's protocol.

## Notes

- Voice input uses the browser Web Speech API and works best in Chrome or Edge.
- WebMCP support depends on the browser environment and the available WebMCP implementation.
