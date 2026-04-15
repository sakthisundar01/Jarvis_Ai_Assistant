# JARVIS — Voice AI Assistant

> *"Sometimes you gotta run before you can walk."*

A real-time, low-latency voice assistant inspired by Tony Stark's JARVIS. Speaks. Listens. Thinks. Calls tools.

## Stack

| Layer | Technology |
|-------|------------|
| Speech-to-Text | **Sarvam** (Indic-language friendly) |
| Language Model | **Google Gemini 2.5 Flash-Lite** |
| Text-to-Speech | **Deepgram Aura** |
| Realtime Transport | **LiveKit** |
| Tool Calling | **FastMCP** |

## Setup

1. Clone this repo
2. Copy `.env.example` to `.env` and fill in your API keys
3. Install dependencies:
```bash
   uv sync
```
4. Run the agent:
```bash
   python main.py
```

## Architecture

JARVIS runs as a LiveKit agent that streams audio bidirectionally. Incoming audio hits Sarvam STT, the transcript flows into Gemini Flash-Lite (with FastMCP tools attached for actions), and the response is spoken back through Deepgram Aura — all in real time.

## Roadmap

- [ ] Add custom MCP tools
- [ ] Multi-language support via Sarvam
- [ ] Voice persona tuning
- [ ] Memory / context persistence

## Acknowledgments

Built on the foundation of [SAGAR-TAMANG/friday-tony-stark-demo](https://github.com/SAGAR-TAMANG/friday-tony-stark-demo) by [Sagar Tamang](https://github.com/SAGAR-TAMANG). The original FRIDAY agent scaffolding, LiveKit integration, and MCP server setup are his work — this fork swaps the model stack and rebrands the assistant. Huge thanks for open-sourcing such a clean starting point.

---

Built by [Sakthi Sundar R](https://github.com/sakthisundar01)
