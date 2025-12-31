# Architecture

This repository documents the integration of TradingView Advanced Charts into MarketCriptoLabs internal tools.

## Goals
- Embed TradingView Advanced Charts into an internal analytics UI
- Keep TradingView library files and credentials private (not exposed in public repos)
- Provide a clear separation between UI, integration layer, and optional backend proxy

## High-level components
1. **Frontend (web UI)**
   - Hosts the chart container
   - Handles user interactions, routing, and UI controls
   - Loads TradingView Advanced Charts (once approved)

2. **Integration layer**
   - Chart initialization/config
   - Datafeed adapter (if custom datafeed is used)
   - Auth/session handling (if required)

3. **Optional Backend (recommended if client-facing)**
   - Protects secrets
   - Proxies requests (if needed)
   - Issues short-lived tokens/session info to frontend

## Repo structure (planned)
- `/frontend` — UI application (React recommended)
- `/charts` — integration layer, widget bootstrap, and configs
- `/docs` — notes and internal documentation

## Security notes
- Never commit TradingView library files or license keys to a public repo
- Use environment variables and private storage for sensitive data
- Prefer a backend proxy for any client-facing deployment

## Status
Work in progress.
