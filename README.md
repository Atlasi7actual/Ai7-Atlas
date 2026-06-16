# Ai7-Atlas

# 📡 The Air-Gapped Science Terminal (Local-First AI Spine)

A rugged, high-contrast, conversational interface terminal designed for physics, astrophysics, calculus, and hydrology compute workloads. Run an elite scientific workspace entirely on your own silicon—zero cloud dependencies, zero data tracking, zero subscription traps.

## ⚡ The Architecture: "Bring Your Own Brain"
This software is a **pure local execution spine**. It completely decouples the user interface and deterministic mathematical processing from the underlying language model inference engine. 

* **Local Mode:** Handshake directly with your local `Ollama` runtime running optimized models (`qwen2.5:3b`, `llama3`, etc.).
* **Uplink Mode:** Drop in your personal cloud API keys (`Claude / Anthropic`, `OpenAI`) to scale up to maximum reasoning power on the fly.
* **Deterministic Compute:** Language models handle natural language interaction, while a dedicated local Python matrix executes exact scientific formulas flawlessly (e.g., fluid dynamics, orbital mechanics, escape velocity).


## What you need

- **Windows 10/11**
- **Ollama** — a free local AI runtime: <https://ollama.com/download>
- One chat model (a ~2 GB download; instructions below)

---

## Quick start (3 steps)

### 1. Install Ollama
Download and run the installer from <https://ollama.com/download>, then launch it.
Ollama runs quietly in the background.

### 2. Pull a model
Open a terminal (PowerShell) and run:

```powershell
ollama pull qwen2.5:3b
```

That's the default Mr. Science looks for — small, fast, and capable. Prefer something
beefier and have the RAM? Any chat model works, e.g.:

```powershell
ollama pull qwen2.5:7b      # larger, a bit sharper
ollama pull llama3.2        # a popular alternative
```

### 3. Launch Mr. Science
**Double-click `MrScience.exe`.** The app starts and opens in your browser — no Python, no
terminal. When the model is found, the AI tutor is ready and you can ask it physics, math, or
chemistry — or punch numbers into the calculator and watch them plot.

> Mr. Science keeps your settings, history, and notes in `data/`, `history/`, and `knowledge/`
> folders right beside the app — back those up to keep them.

---

## Choosing your model in the app

Open **⚙ Settings** in the chat toolbar:

- **Model** — pick any model you've pulled (the list is read live from Ollama). Switching
  takes effect immediately, no restart.
- **Provider** — *Local (Ollama)* today. Cloud options are on the way.
- **Chat warmth / context** — optional tuning.

Your choice is saved and remembered next launch.

---

## If the tutor says it isn't ready

A banner above the chat tells you the one thing to fix. Here's every case:

| Banner says | What to do |
|---|---|
| **No local AI runtime found.** | Install Ollama (free), launch it, then reopen Mr. Science: <https://ollama.com/download> |
| **Ollama is running, but no models are installed yet.** | Run `ollama pull qwen2.5:3b` to download one. |
| **Your selected model "…" isn't installed.** | Run `ollama pull <that model>`, or pick a model you already have in ⚙ Settings. |
| **Ready — narrating with …** | You're all set. 🎉 |

The banner disappears on its own once a model is ready.

---

## Prefer the cloud? (optional)

Don't want to run a local model? Mr. Science can use **Claude (Anthropic's cloud API)** instead — no local model, no CPU load on your machine.

1. Install the cloud support: `pip install anthropic`
2. In **⚙ Settings**, set **Provider → Claude (cloud API)**, pick a model (Opus is strongest; Sonnet/Haiku are cheaper), and paste your Anthropic API key (from <https://console.anthropic.com>).
3. Turn **network access ON** in Settings — cloud needs the internet, and Mr. Science keeps it **off by default** (offline-first).

The math stays exactly as accurate either way — it's grounded by the engine, not the model.

---

## What works with no model at all

Even before you install anything, these run **100% offline**:

- **Calculator** — algebra, calculus, solve/factor/expand/limit (exact + decimal)
- **Formula rack (ATLAS)** — dozens of validated science instruments
- **Plotting & the wave lab** — functions, parametric/polar curves, live waveforms

Only the conversational **AI tutor** needs a model.

---

## Privacy

Mr. Science is **offline-first**. It never reaches the internet for weather or location
data unless you explicitly turn that on. Your chats, your notes, and your model all stay
on your machine.
