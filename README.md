# Weather MCP Server

A small [Model Context Protocol](https://modelcontextprotocol.io) server, written in Python, that gives
Claude (or any MCP client) live US weather data from the [National Weather Service API](https://www.weather.gov/documentation/services-web-api).

## Tools

| Tool | What it does |
| --- | --- |
| `get_alerts(state)` | Active weather alerts for a two-letter US state code (e.g. `CA`) |
| `get_forecast(latitude, longitude)` | Forecast for the next few periods at a location |

## Setup

Requires Python 3.13+ and [uv](https://docs.astral.sh/uv/).

```bash
uv sync
uv run weather.py
```

## Use with Claude Desktop

Add the server to `claude_desktop_config.json` (an example is in this repo), replacing the path:

```json
{
  "mcpServers": {
    "weather": {
      "command": "uv",
      "args": ["--directory", "/ABSOLUTE/PATH/TO/weather", "run", "weather.py"]
    }
  }
}
```
