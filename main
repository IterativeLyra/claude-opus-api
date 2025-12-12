from fastapi import FastAPI, Request
import httpx
import os

app = FastAPI()
ANTIGRAVITY_KEY = os.getenv("ANTIGRAVITY_API_KEY")
CLAUDE_API_URL = "https://chat-api.antigravity.space/api/chat"

@app.post("/v1/chat/completions")
async def proxy_claude(request: Request):
    body = await request.json()
    headers = {
        "Authorization": f"Bearer {ANTIGRAVITY_KEY}",
        "Content-Type": "application/json"
    }
    async with httpx.AsyncClient() as client:
        response = await client.post(CLAUDE_API_URL, headers=headers, json=body)
    return response.json()
