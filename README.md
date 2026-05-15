🌐 [Português (BR)](README.pt_BR.md) | [Español](README.es.md)

---

# 🎯 Soc Ops

### The Social Bingo Game That Gets People Talking

Break the ice at your next event with **Soc Ops** – a dynamic, interactive bingo game that brings people together. Match strangers with fun prompts, find 5 in a row, and watch your mixer come alive.

Perfect for:
- 🎓 Conference icebreakers
- 🤝 Team building events  
- 🎉 Networking mixers
- 👥 Community gatherings
- 💡 Corporate all-hands

---

## ⚡ Quick Start

```bash
# Install dependencies
uv sync

# Start the development server
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000

# Navigate to http://localhost:8000 and start playing!
```

---

## 🎮 How It Works

1. **Load the game** – Host opens Soc Ops on a projector or shared screen
2. **Players receive prompts** – Questions like "Find someone who's been to 5+ countries" appear
3. **Network and match** – Attendees mingle and find people who match each prompt
4. **Get 5 in a row** – Complete horizontal, vertical, or diagonal rows to win
5. **Have fun** – Repeat and celebrate the connections made!

---

## 🛠️ Tech Stack

Built with modern Python tooling for rapid development:

- **FastAPI** – Lightning-fast, modern web framework
- **Jinja2** – Elegant templating
- **HTMX** – Smooth, interactive UX without heavy JavaScript
- **SQLite** – Simple, reliable data persistence

---

## 📚 Learning Path: Copilot-Powered Development

This is more than just a game – it's a **complete workshop** for mastering AI-assisted development with GitHub Copilot.

| Step | Focus | What You'll Learn |
|------|-------|------------------|
| **[00: Overview](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview)** | 🎯 Setup & Checklist | Prerequisites and project structure |
| **[01: Context Engineering](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=01-setup)** | 🧠 AI Foundations | Crafting effective prompts for Copilot |
| **[02: Design-First Frontend](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=02-design)** | 🎨 UI/UX Magic | Building beautiful interfaces with AI assistance |
| **[03: Custom Quiz Master](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=03-quiz-master)** | 🤖 Custom Agents | Creating specialized Copilot agents for your workflow |
| **[04: Multi-Agent Development](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=04-multi-agent)** | 🚀 Advanced Patterns | Orchestrating multiple AI agents in production |

💡 **New to the workshop?** Start with **[Part 00: Overview](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview)** – it includes all prerequisites and setup.

📝 Prefer offline reading? Lab guides are also available in the [`workshop/`](workshop/) folder.

---

## 💻 Development

### Key Commands

```bash
uv sync              # Sync dependencies
uv run pytest        # Run tests
uv run ruff check .  # Lint code
uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000  # Start server
```

### Project Structure

```
soc-ops/
├── app/                    # Backend & frontend
│   ├── static/            # CSS and assets
│   ├── templates/         # Jinja2 templates
│   ├── game_logic.py      # Bingo rules engine
│   ├── game_service.py    # Game session management
│   └── main.py            # FastAPI app
├── tests/                 # Test suite
├── workshop/              # Lab guide content
└── pyproject.toml         # Dependencies & config
```

---

## 🎓 Perfect For

- **Developers** learning AI-assisted development workflows
- **Teams** seeking fun networking activities
- **Organizations** hosting large-scale events
- **Educators** teaching modern Python + AI practices

---

## 🤝 Contributing

We welcome contributions! See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## 📜 License

Licensed under [MIT](LICENSE)

## 🆘 Support

- 📖 Check the [lab guides](workshop/)
- 🐛 Found an issue? See [SUPPORT.md](SUPPORT.md)
- 💬 Questions? Open a discussion or issue

---

**Ready to get started?** → **[Begin Part 00: Overview](https://copilot-dev-days.github.io/agent-lab-python/docs/step.html?step=00-overview)**
