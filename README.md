# Lifeline — Dialysis Companion

A browser-based companion chatbot prototype for a dialysis center. It offers supportive conversation and general, sourced education about hemodialysis, access care, food and fluids, and treatment routines. Lifeline is a fictional demo and does not represent a real center or verify any facility details.

## Run locally

Requires Python 3.9+. Install dependencies with `python -m pip install -r requirements.txt`, then run `python app.py` and open http://127.0.0.1:5000.

A Gemini key is optional. Add `GEMINI_API_KEY` to a private `.env` file to enable generated replies; without a key, the app uses its reviewed knowledge-base fallback. Never commit API keys.

With Gemini configured, Lifeline is intended to answer a broad range of dialysis-related questions even when the exact question is not covered by the reviewed knowledge base. Retrieved passages ground answers when available; otherwise the model can answer from general knowledge. It must defer personal diagnosis, treatment changes, medicine instructions, and individual diet or fluid limits to the person's care team. Provider failures are reported in the server log and the chat gives a retry message instead of presenting an empty-source fallback as an answer.

## Scope and safety

Lifeline is not a doctor, nurse, dialysis unit, or emergency service. It cannot assess symptoms or provide individual dialysis, medicine, diet, or fluid instructions. For personal guidance, contact the patient's dialysis team. For chest pain, severe breathing difficulty, fainting, signs of stroke, or severe bleeding, call local emergency services. The prototype uses 911 as a Philippines demo number; verify local emergency details before deployment.

Conversation history stays in the browser tab and is sent to the configured AI provider for replies; the app does not write chat logs. Avoid sharing names or identifying details. No center name, address, schedule, contact number, prices, or available services are configured. Add verified details only after confirmation by the actual center. See `references.md` for source notes.
