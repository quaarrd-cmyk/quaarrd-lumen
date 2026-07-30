# 🔆 Lumen — Adaptive AI Tutor

Built for the **Prometheus July AI Challenge** (Devpost)

Lumen is an AI-powered tutor that explains any concept at the depth *you* actually need — then helps you lock it in with auto-generated diagrams, quizzes, and flashcards. No two learners are the same, so no explanation should be either.

**Live app:** https://vct8knrn.streamlit.app

---

## The Problem

Most AI explanations are one-size-fits-all. A 10-year-old and a graduate student asking "how do processors work?" get the same wall of text — too simple for one, too dense for the other. Lumen fixes this by adapting explanation depth on demand, and turns passive reading into active learning with built-in testing tools.

## Features

- 🎚️ **Adaptive explanation levels** — Kid / Student / Expert, switchable anytime, same question yields genuinely different depth
- 🖼️ **Real labeled diagrams** — auto-generates flowcharts with actual legible text (via Mermaid.ink), not garbled AI-image text
- 📝 **Auto-generated quizzes** — 3 multiple-choice questions per topic, with instant feedback and explanations
- 🗂️ **Flashcards** — key terms and definitions generated on demand for quick review
- 📎 **Image upload & analysis** — snap a photo of homework, a textbook page, or notes and get it explained
- 💾 **Persistent sessions** — no login required; a short session code (or your own custom one) saves your entire history, restorable on any device
- 📝 **Notes scratchpad** — jot down reminders or key points, saved alongside your session

## Tech Stack

- **Frontend/Backend:** [Streamlit](https://streamlit.io/) (Python)
- **Language model:** Groq API — `openai/gpt-oss-120b` (explanations, quizzes, flashcards) and `qwen/qwen3.6-27b` (vision/image analysis)
- **Diagrams:** Groq-generated content rendered through [Mermaid.ink](https://mermaid.ink/) for crisp, real text labels
- **Image generation fallback:** Pixazo (Flux Schnell) for symbolic visuals when a labeled diagram isn't possible
- **Persistence:** Google Firebase Firestore, keyed by session code (no accounts, no OAuth)
- **Image hosting:** ImgBB (for saved diagrams across sessions)

## How It Works

1. Start a session — get a short code, or set your own memorable one
2. Ask about any concept, at your chosen level
3. Optionally: visualize it, quiz yourself, generate flashcards, or upload an image for analysis
4. Everything saves automatically — resume anytime by re-entering your code or reopening a bookmarked link

## Running Locally

```bash
git clone https://github.com/quaarrd-cmyk/quaarrd-lumen.git
cd quaarrd-lumen
pip install -r requirements.txt
streamlit run app.py
```

You'll need to provide your own `secrets.toml` with:
```toml
GROQ_API_KEY = "..."
PIXAZO_API_KEY = "..."
IMGBB_API_KEY = "..."

[firebase]
# Firebase service account credentials
```

## Team

Built solo by [Munkar](https://github.com/quaarrd-cmyk) under the **Quaarrd** brand, forked and adapted from an existing project (Qwill AI) for this hackathon.

---

*Submitted for the Prometheus July AI Challenge — an educational AI tool built to make learning more accessible, engaging, and personalized.*
# quaarrd-lumen
For Prometheus Hackathon 
