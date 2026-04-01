# selu-agent-weather

Weather forecast agent for [Selu](https://github.com/selu-bot/selu).

Provides real-time weather forecasts using the free [Open-Meteo](https://open-meteo.com/) API.
This is the primary test and validation agent for the Selu platform.

## Capabilities

- **weather-api** -- `get_forecast` tool that geocodes city names and fetches current conditions plus multi-day forecasts.

## Permission Model

This agent declares the following permission-related configuration:

- **Tool policy**: `get_forecast` has `recommended_policy: allow` (safe, read-only weather data from a free public API).
- **Network**: Strict allowlist -- only `api.open-meteo.com:443` and `geocoding-api.open-meteo.com:443`.
- **Filesystem**: `temp` only (no persistent storage).
- **Credentials**: None required (Open-Meteo is free, no API key needed).
- **Resources**: 64 MB RAM, 0.25 CPU, 15s CPU time, 32 PIDs.

During installation, the Selu setup wizard will prompt the user to review and confirm the tool policy for `get_forecast` (pre-selected to "allow" per the recommendation) as well as the built-in `emit_event` and `delegate_to_agent` tools.

## Installation

Install this agent from the Selu marketplace UI

No configuration required -- Open-Meteo is a free API with no API key needed.
