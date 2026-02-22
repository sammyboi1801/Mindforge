```
███╗   ███╗██╗███╗   ██╗██████╗ ███████╗ ██████╗ ██████╗  ██████╗ ███████╗
████╗ ████║██║████╗  ██║██╔══██╗██╔════╝██╔═══██╗██╔══██╗██╔════╝ ██╔════╝
██╔████╔██║██║██╔██╗ ██║██║  ██║█████╗  ██║   ██║██████╔╝██║  ███╗█████╗  
██║╚██╔╝██║██║██║╚██╗██║██║  ██║██╔══╝  ██║   ██║██╔══██╗██║   ██║██╔══╝  
██║ ╚═╝ ██║██║██║ ╚████║██████╔╝██║     ╚██████╔╝██║  ██║╚██████╔╝███████╗
╚═╝     ╚═╝╚═╝╚═╝  ╚═══╝╚═════╝ ╚═╝      ╚═════╝ ╚═╝  ╚═╝ ╚═════╝ ╚══════╝
```

<div align="center">

**⚔ MULTI-AGENT INTELLIGENCE SYSTEM ⚔**

*Watch AI agents think, argue, vote, and forge answers together — live in your browser*

[![Status](https://img.shields.io/badge/STATUS-ONLINE-00ff88?style=for-the-badge&labelColor=050508)](.)
[![Zero Backend](https://img.shields.io/badge/BACKEND-ZERO-00e5ff?style=for-the-badge&labelColor=050508)](.)
[![Providers](https://img.shields.io/badge/PROVIDERS-GROQ_%7C_OPENROUTER_%7C_OLLAMA-ff6b35?style=for-the-badge&labelColor=050508)](.)
[![License](https://img.shields.io/badge/LICENSE-MIT-b44fff?style=for-the-badge&labelColor=050508)](.)

</div>

---

## ▶ WHAT IS THIS

MINDFORGE is a **single-file, zero-backend multi-agent reasoning playground** that runs entirely in your browser.

You define a team of AI agents, pick a reasoning architecture, give them a task — then watch them **actually talk to each other**, disagree, reference each other by name, vote democratically, and forge a synthesized final answer.

It's not just smarter outputs. It's **intelligence you can watch happen.**

> Multiple small models reasoning together consistently outperform a single larger model on complex tasks. This is the "Mixture of Agents" finding from the Together AI research paper. MINDFORGE makes that research interactive and fun.

---

## ⚡ QUICK START

```bash
# No install. No npm. No backend. Just open it.
open mindforge.html
```

That's it. Drop in a Groq API key (free at [console.groq.com](https://console.groq.com)) and hit **FORGE IT**.

Or run with no API key at all — demo mode kicks in automatically with mock agent responses.

---

## 🔌 MODEL PROVIDERS

MINDFORGE supports three providers switchable from the UI — no code changes needed.

### GROQ *(recommended for speed)*
- Free tier available at [console.groq.com](https://console.groq.com)
- Models: `llama-3.1-8b-instant`, `llama-3.1-70b-versatile`, `gemma2-9b-it`, `mixtral-8x7b`
- Insanely fast inference — agents respond in ~1-2 seconds each

### OPENROUTER *(recommended for model variety)*
- Access 100+ models from one API key at [openrouter.ai](https://openrouter.ai)
- Free models available: `meta-llama/llama-3.1-8b-instruct:free`, `mistralai/mistral-7b-instruct:free`, `google/gemma-2-9b-it:free`
- Paid models: Claude, GPT-4o, Gemini Pro and more

### OLLAMA *(recommended for privacy / local)*
- Run models 100% locally — zero data leaves your machine
- Setup:
  ```bash
  # Install ollama from ollama.ai, then:
  ollama serve
  ollama pull llama3.2
  # Set host in UI: http://localhost:11434
  ```
- Any model you've pulled works: `llama3.2`, `mistral`, `phi3`, `gemma2`, etc.

---

## 🏗 ARCHITECTURES

Five reasoning architectures, each backed by research on how collaborative AI improves output quality.

### 🏛 COUNCIL *(Mixture of Agents)*
All agents independently form opinions in Round 1. In Round 2 they read every other agent's response and revise their position — explicitly addressing peers by name. Round 3 is a democratic vote. A synthesizer produces the final answer crediting individual contributions.

**Best for:** Open-ended problems, strategy, creative work, anything with no single right answer.

---

### ⚖ JURY / DEBATE
Agents are split into opposing sides. They make opening arguments, then cross-examine each other directly. A Judge agent reads the full debate and delivers a reasoned verdict.

**Best for:** Decisions, comparisons, "should I do X", evaluating options.

---

### 🔗 PIPELINE
Sequential handoff chain. Each agent reads all prior work and adds their specialist perspective before passing it forward. Output quality compounds through the chain.

**Best for:** Structured tasks — writing, code, research reports, anything with clear stages.

---

### ⭐ STAR / HUB
A Manager agent briefs the team, assigning each agent a specific subtask. Specialists execute in order, reading each other's outputs. Manager synthesizes everything at the end and credits the team.

**Best for:** Complex multi-part problems, project planning, anything that needs coordination.

---

### ⚡ CHAOS
All agents fire simultaneously with high temperature. Raw, unfiltered, fast. A Synthesizer agent reads all outputs and extracts signal from the noise — calling out the strongest ideas by agent name.

**Best for:** Brainstorming, breaking out of conventional thinking, creative divergence.

---

## 🤖 AGENT SYSTEM

### Roles
Each agent has a **role** that shapes how the model responds. Available roles:

`Researcher` · `Critic` · `Engineer` · `Visionary` · `Skeptic` · `Optimist` · `Devil's Advocate` · `Analyst` · `Synthesizer` · `Judge` · `Defender` · `Prosecutor` · `Philosopher` · `Manager` · `Security Expert` · `Market Analyst` · `Scientist` · `Writer`

### Per-Agent Config
- **Temperature** — how creative vs. precise the agent's reasoning is
- **Aggression** — how hard the agent pushes back on peers (low = collaborative, high = combative)

### True Conversation Threading
Every agent call includes the **full shared conversation history** as proper multi-turn context — not a dumped text block. Each agent:
- Knows who all other agents are by name and role from the start
- Reads every prior message in structured assistant-turn format
- Is explicitly instructed to address peers by name and react to what was just said

This is the difference between agents that *monologue in parallel* vs agents that *actually talk to each other.*

---

## 🎮 FEATURES

| Feature | Description |
|---|---|
| ⌨ **Typing Animation** | Each agent's message types out character by character with a live cursor. Toggleable. |
| 🔊 **Voice Mode** | Browser's built-in Web Speech API reads agents aloud. Each agent gets a distinct pitch. Free, no API key. |
| 🗳 **Democratic Voting** | Animated vote bars after Council deliberation. Weighted by agent confidence. |
| 💭 **Secret Thoughts** | Every message has a hidden reasoning layer. Click the lock to reveal what the agent was "really thinking." |
| 🎯 **Live Intervention** | Pause mid-session and send a direct message to any agent. They incorporate it in their next turn. |
| 📊 **Contribution Breakdown** | Every synthesis card shows which agents contributed most to the final answer. |
| 📡 **Live Status Panel** | Real-time agent state — IDLE, THINKING, READING, VOTING, DONE — with confidence bars. |
| 🗂 **Session History** | Last 10 sessions saved locally. Click to reload any past task. |
| 🎨 **Pixel Art Avatars** | Each agent gets a procedurally generated pixel art avatar. |

---

## 🎯 PRESETS

Six one-click configurations that set agents, roles, and architecture together:

| Preset | Agents | Architecture | Best For |
|---|---|---|---|
| 🚀 **Startup Team** | Visionary, Skeptic, Engineer, Market Analyst | Council | Product & business ideas |
| ⚔ **Debate Club** | Prosecutor, Defender, Judge | Jury | Decisions & comparisons |
| 🔬 **Research Lab** | Gatherer, Analyst, Critic, Synthesizer | Pipeline | Deep analysis |
| 💻 **Code Review** | Architect, Engineer, Security, Optimizer | Pipeline | Technical problems |
| 🔮 **Oracle** | Empiricist, Idealist, Devil's Advocate, Moderator | Star | Hard / philosophical questions |
| 💀 **Chaos Mode** | Alpha, Beta, Gamma, Delta, Epsilon | Chaos | Brainstorming |

---

## 🧠 WHY MULTIPLE AGENTS ACTUALLY WORK

This isn't just a fun demo — the reasoning improvement is real and documented:

**Mixture of Agents (Together AI, 2024):** Multiple LLMs collaborating with a synthesis layer beat GPT-4 on benchmarks using only open-source models.

**Why it works mechanically:**
1. **Independent priors** — agents form opinions without groupthink contamination
2. **Error catching** — a second agent reading the first's reasoning catches logical bugs the first model missed
3. **Role priming** — the same base model responds very differently when primed as a Skeptic vs. a Visionary. Role diversity = reasoning diversity.
4. **Forced revision** — making an agent explicitly read and respond to peer arguments produces substantially better outputs than a single-pass generation

MINDFORGE implements all four of these effects.

---

## 📁 STRUCTURE

```
mindforge.html          — the entire application (single file)
README.md               — you are here
```

Everything lives in one HTML file:
- Pixel art dark theme (CSS variables, scanline overlay, pixel grid)
- React Flow-style agent canvas (vanilla JS + DOM)
- All 5 architecture orchestration engines
- Provider abstraction layer (Groq / OpenRouter / Ollama)
- Typing animation engine
- Web Speech API voice system
- Lightweight markdown renderer
- Session history (localStorage)

---

## 🛣 ROADMAP

Things that would make this significantly more powerful:

- [ ] **FastAPI + LangGraph backend** — proper server-side orchestration, streaming WebSockets, rate limiting
- [ ] **React + React Flow frontend** — visual drag-and-drop agent graph builder
- [ ] **Agent memory** — agents that remember past sessions and build relationships over time
- [ ] **Agent marketplace** — community-shared agent configs (Finance Expert, Medical Analyst, etc.)
- [ ] **Streaming tokens** — see each word appear as it's generated
- [ ] **Export** — download session transcripts as PDF or markdown
- [ ] **Multiplayer** — two users each control a team of agents, race to solve a problem
- [ ] **Reputation system** — agents gain/lose credibility scores based on how often their arguments win votes

---

## 🤝 CONTRIBUTING

MINDFORGE is intentionally kept as a single HTML file for maximum accessibility — no build step, no dependencies, just open and use.

If you want to contribute:
1. Fork the repo
2. Make changes to `mindforge.html`
3. Test with at least two different providers
4. Submit a PR with a description of what changed and why

Ideas especially welcome for: new architectures, new agent roles, UI improvements, prompt engineering improvements.

---

## ⚖ LICENSE

MIT — do whatever you want with it. If you build something cool, let us know.

---

<div align="center">

**Built with 🧠 and way too much coffee**

*"The whole is greater than the sum of its parts — especially when the parts argue with each other."*

</div>
