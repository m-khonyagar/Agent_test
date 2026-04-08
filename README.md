# Agent_test

Experimental agent MVP built around the OpenAI Responses API.

## Status
This repository is an experimental sandbox for agent workflows, browser tooling, local bridge actions, and approval-gated execution. It should be treated as a development prototype, not a production-ready platform.

## Includes
- Agent loop + function tools + `web_search_preview`
- Playwright browser actions for online execution
- Workspace-constrained local bridge
- FastAPI task endpoints with approval flow for sensitive actions

## Setup (Windows PowerShell)
```bash
python -m venv .venv
. .venv/Scripts/activate
pip install -r requirements.txt
playwright install chromium
Copy-Item .env.example .env
mkdir workspace
```

Set `OPENAI_API_KEY` in `.env`.

## API Run
```bash
uvicorn api:app --reload --port 8000
```

## Notes
- `WORKSPACE_ROOT=./workspace`
- `ALLOW_LOCAL_WRITE=false`
- `ALLOW_SCRIPT_EXECUTION=false`
- Approval and task storage are in-memory in this MVP
- Sensitive actions still remain policy-gated even after approval