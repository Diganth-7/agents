# Assignment 2 — ReAct Agent with a Search Tool

This project implements a simple **ReAct (Reason + Act) agent** using the Gemini API. Gemini can decide when to call a Python search tool, inspect the returned documents, and produce a final answer.

## Files

- `ReAct_Agent_Assignment_2_FIXED.ipynb` — complete Google Colab/Jupyter notebook.
- `requirements.txt` — Python dependency.
- `.gitignore` — ignores local secrets and generated files.

## Run in Google Colab

1. Open [Google Colab](https://colab.research.google.com/).
2. Select **File → Open notebook → GitHub** and paste this repository URL:
   https://github.com/Diganth-7/agents
3. Open `ReAct_Agent_Assignment_2.ipynb`.
4. Create a Gemini API key in [Google AI Studio](https://aistudio.google.com/app/apikey).
5. In Colab, optionally add a secret named `GOOGLE_API_KEY`. Otherwise, the notebook securely prompts for the key.
6. Run all cells from top to bottom.

## How it works

1. A question is sent to Gemini.
2. Gemini can request the `search_documents` function.
3. Python searches the local AI knowledge base and returns matching documents.
4. The tool result is sent back to Gemini.
5. Gemini produces the final response.

The search tool searches only the notebook's local knowledge base; it does **not** perform a live web search.

## Run locally

Python 3.10+ is recommended.

```bash
pip install -r requirements.txt
jupyter notebook
```

Then open `ReAct_Agent_Assignment_2.ipynb` and run its cells. When prompted, enter your Gemini API key.

## Security

- Never commit API keys, `.env` files, or Colab secret values.
- The notebook uses a hidden prompt for a key when Colab Secrets are unavailable.
- If an API key is accidentally exposed, revoke it in Google AI Studio and create a new one.

## Notes

The notebook uses Google's `google-genai` SDK and the `gemini-3.8-flash` model alias. Model availability depends on the Gemini API account and may change. If needed, change `MODEL_NAME` to a function-calling-capable model available to your account.
