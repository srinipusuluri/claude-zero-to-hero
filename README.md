<div align="center">

# 🚀 Claude Zero to Hero

### Master agentic AI development with Claude — domain by domain

[![License: MIT](https://img.shields.io/badge/License-MIT-6d5dfc.svg)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude%20Code-v2.1+-00d4ff.svg)](https://claude.ai)
[![MCP](https://img.shields.io/badge/MCP-Ready-ff6ec7.svg)](https://modelcontextprotocol.io)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-2ee6a0.svg)](https://github.com/srinipusuluri/claude-zero-to-hero/pulls)

---

[**🌐 Live Portal**](https://srinipusuluri.github.io/claude-zero-to-hero) •
[**📚 Learn**](#-learning-tracks) •
[**⌨️ Commands**](#-commands-reference) •
[**💡 Agent Ideas**](#-50-agent-ideas) •
[**🎓 Certification**](#-certification-exam)

</div>

---

## 🌟 What is This?

**Claude Zero to Hero** is a comprehensive, hands-on learning portal for mastering agentic AI development with [Claude](https://claude.ai) by Anthropic. Whether you're setting up your first Claude Code session or architecting multi-agent systems, this guide takes you from zero to deployment-ready.

> **Built for learning by doing** — each section includes copy-ready commands, code examples, and interactive practice questions.

---

## 🗺️ Learning Tracks

<table>
<tr>
<td align="center" width="20%">🚀<br><b>Prerequisites</b><br><sub>Set up in 15 min</sub></td>
<td align="center" width="20%">📚<br><b>5 Core Domains</b><br><sub>Deep dive</sub></td>
<td align="center" width="20%">🔬<br><b>Internals</b><br><sub>Under the hood</sub></td>
<td align="center" width="20%">💡<br><b>50 Agent Ideas</b><br><sub>Build something</sub></td>
<td align="center" width="20%">🎓<br><b>Certification</b><br><sub>Prove your skills</sub></td>
</tr>
</table>

### 🚀 Quick Start — 6 Steps

| # | Step | Time |
|---|------|------|
| ① | **Subscribe to Claude Pro** at [claude.ai](https://claude.ai) | ~5 min |
| ② | **Install VS Code & Node.js 18+** | ~5 min |
| ③ | **Install Claude Code** — `npm install -g @anthropic-ai/claude-code@latest` | ~1 min |
| ④ | **Set up VS Code Extension** — Search "Claude Code" in Extensions | ~3 min |
| ⑤ | **Learn Essential Commands** — `/help`, `/init`, `/clear`, `/model` | reference |
| ⑥ | **Build 3 Starter Projects** — Vibe App, Workflow, Agent Prompt | hands-on |

```bash
# Fast track — verify your environment
node --version  # need v18+
npm --version   # need v9+
npm install -g @anthropic-ai/claude-code@latest
claude --version
```

---

## 📖 5 Core Domains

### ⚙️ Agentic Architecture & Orchestration
```
┌─────────────────────────────────────────────────┐
│           Agent Patterns at a Glance             │
├─────────────┬───────────────────┬───────────────┤
│  Single     │  Orchestrator–    │  Evaluator–   │
│  Agent Loop  │  Worker           │  Optimizer    │
│  (ReAct)    │  (Parallel)       │  (Self-crit)  │
└─────────────┴───────────────────┴───────────────┘
```
- **Single-Agent Loops** — model reasons → calls tool → observes → loops
- **Multi-Agent / Orchestrator–Worker** — lead agent decomposes & delegates
- **Workflows vs. Agents** — predefined paths vs. autonomous direction
- **Routing & Evaluator-Optimizer** — classify input, self-critique outputs
- **State, Memory & Handoffs** — durable logs, context passing, resume

### 🔧 Tool Design & MCP Integration
```
Tools → MCP Servers → Claude → Actions → Results
```
- **Tool Definition & JSON Schema** — names, descriptions, input schemas
- **Model Context Protocol (MCP)** — "USB-C for AI" — open standard
- **Building an MCP Server** — `FastMCP` SDK, stdio/SSE transport
- **Connecting MCP in Claude** — config in `mcpServers`
- **Tool Reliability & Error Handling** — structured errors, idempotency

### 💻 Claude Code Configuration & Workflows
| Component | Purpose | Location |
|-----------|---------|----------|
| `CLAUDE.md` | Project memory — stack, commands, conventions | Project root |
| Custom Slash Commands | Reusable prompt templates | `.claude/commands/` |
| Subagents | Specialized roles with own prompts | `.claude/agents/` |
| Hooks | Lifecycle event scripts | `.claude/hooks/` |
| Permissions | Auto-run control | `.claude/settings.json` |

### 📝 Prompt Engineering & Structured Output
- **XML Tags** — Claude is tuned to respect them for structure
- **Few-Shot + Chain-of-Thought** — 2-5 examples, reasoning scratchpad
- **Guaranteed JSON** — define a tool whose schema IS your output
- **Prefilling** — start assistant turn with `{` to lock format
- **System Prompts** — carry more weight than inline instructions

### 🧠 Context Management & Reliability
```
Context Window Budget
┌──────────────────────────────────────────────┐
│ System │ Conversation │ Tools │ Open Files   │
├──────────────────────────────────────────────┤
│ Maximize by: caching, RAG, compaction, trim  │
└──────────────────────────────────────────────┘
```
- **Prompt Caching** — mark stable prefixes with `cache_control`
- **RAG** — retrieve relevant chunks, don't stuff everything in
- **Compaction** — `/compact` summarizes old turns
- **Retries & Idempotency** — exponential backoff, safe retries
- **Evals & Observability** — measure before you improve

---

## ⌨️ Commands Reference

<details>
<summary><b>🌱 Getting Started</b> — basic commands</summary>

| Command | Description |
|---------|-------------|
| `/init` | Scan codebase & generate CLAUDE.md |
| `/help` | List all commands for your version |
| `/status` | Show account, model, version, CWD |
| `/model` | Switch active model (opus/sonnet/haiku) |
| `/memory` | View/edit layered CLAUDE.md files |
</details>

<details>
<summary><b>💬 Session & Context</b> — manage conversations</summary>

| Command | Description |
|---------|-------------|
| `/clear` | Wipe conversation history (files stay) |
| `/compact` | Summarize history to free tokens |
| `/context` | See context window usage breakdown |
| `/resume` | Reopen a past session |
| `/rewind` | Roll back to a checkpoint |
</details>

<details>
<summary><b>🔍 Review & Quality</b> — code quality tools</summary>

| Command | Description |
|---------|-------------|
| `/review` | Review changed code for bugs/style |
| `/security-review` | Deep scan for injections/secrets |
| `/plan` | Plan mode — propose actions, wait for approval |
</details>

<details>
<summary><b>🧩 Extend</b> — agents, MCP, plugins</summary>

| Command | Description |
|---------|-------------|
| `/agents` | Create/list/manage subagents |
| `/mcp` | View/connect MCP servers |
| `/plugin` | Install bundles of commands/skills/hooks |
| `/skills` | List auto-invoked workflows |
</details>

<details>
<summary><b>📊 Cost & Insights</b></summary>

| Command | Description |
|---------|-------------|
| `/cost` | Token spend for current session |
| `/usage` | Plan limits & quota remaining |
| `/insights` | Aggregated analytics across sessions |
</details>

---

## 💡 50 Agent Ideas

### 🤝 CRM & Customer-Facing (25 Ideas)

| # | Idea | # | Idea |
|---|------|---|------|
| 01 | Lead Qualification Agent | 14 | Call Coaching Agent |
| 02 | Auto Meeting-Notes Logger | 15 | RFP Responder |
| 03 | Deal Risk Early-Warning | 16 | Renewal-Prep Agent |
| 04 | Personalized Outreach Drafter | 17 | Competitive Battlecard Updater |
| 05 | Tier-1 Support Resolution | 18 | Lead Routing & SLA Agent |
| 06 | Churn-Save Agent | 19 | Knowledge-Base Author |
| 07 | Quote & Proposal Generator | 20 | Multilingual Support Agent |
| 08 | CRM Data Hygiene Agent | 21 | Pipeline Forecast Narrator |
| 09 | Next-Best-Action Recommender | 22 | Abandoned-Cart Recovery |
| 10 | Voice-of-Customer Synthesizer | 23 | Account Research Briefing |
| 11 | Onboarding Concierge Agent | 24 | Survey & NPS Follow-Up |
| 12 | Cross-Sell / Upsell Spotter | 25 | Social Listening & Reply |
| 13 | Sentiment-Aware Escalation Router | | |

### 🏢 Enterprise AI Agents (25 Ideas)

| # | Idea | # | Idea |
|---|------|---|------|
| 26 | Invoice Processing Agent | 39 | Document Migration Agent |
| 27 | Contract Review & Redline | 40 | Code Review & Standards Agent |
| 28 | IT Helpdesk Agent | 41 | Vendor Risk Assessment |
| 29 | Employee Onboarding Orchestrator | 42 | Data Quality Monitoring |
| 30 | Policy & Compliance Q&A | 43 | Knowledge Transfer Agent |
| 31 | Financial Report Analyst | 44 | Sales-Ops Quote-to-Cash |
| 32 | Procurement Sourcing Agent | 45 | Internal Comms Drafting |
| 33 | Meeting Action-Item Tracker | 46 | SOP Generation Agent |
| 34 | Enterprise Search Concierge | 47 | Access Review & Governance |
| 35 | Incident Response Copilot | 48 | Demand Forecasting Agent |
| 36 | Regulatory Change Monitor | 49 | Multi-Agent Research Desk |
| 37 | Expense Audit Agent | 50 | Workflow Exception Handler |
| 38 | Recruiting Screener Agent | | |

---

## 🎓 Certification Exam

Test your knowledge across all 5 domains with a **20-question certification exam**:

- ✅ **Pass mark:** 70% (14/20)
- 🏆 **Earn a certificate** from the ClaudeAI Foundation
- 🔄 **Review wrong answers** and retake anytime
- 📄 **Print or save** your certificate

> Ready? Open the [**portal**](https://srinipusuluri.github.io/claude-zero-to-hero) → click **Certification Exam** tab → enter your name → begin.

---

## 🔗 References

| Domain | Resource |
|--------|----------|
| ⚙️ Agentic Architecture | [Building Effective Agents](https://www.anthropic.com/engineering/building-effective-agents) |
| 🧩 Multi-Agent | [Multi-Agent Research System](https://www.anthropic.com/engineering/multi-agent-research-system) |
| 🔌 MCP | [Model Context Protocol Introduction](https://modelcontextprotocol.io/introduction) |
| ⌨️ Claude Code | [Claude Code Overview](https://docs.anthropic.com/en/docs/claude-code/overview) |
| ⭐ Best Practices | [Claude Code Best Practices](https://www.anthropic.com/engineering/claude-code-best-practices) |
| ✍️ Prompt Engineering | [Prompt Engineering Overview](https://docs.anthropic.com/en/docs/build-with-claude/prompt-engineering/overview) |
| ⚡ Prompt Caching | [Prompt Caching Guide](https://docs.anthropic.com/en/docs/build-with-claude/prompt-caching) |
| 🎯 Context Engineering | [Effective Context Engineering](https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents) |

---

## 🛠️ Project Structure

```
claude-zero-to-hero/
├── README.md              # ← You are here
└── docs/
    └── index.html         # Interactive learning portal
```

---

<div align="center">

### Built with ❤️ for hands-on learning

[**Explore the Portal →**](https://srinipusuluri.github.io/claude-zero-to-hero)

---

<p>
  <a href="https://www.linkedin.com/in/pusulurisrinivasa/">
    <img src="https://img.shields.io/badge/Srinivasa_Pusuluri-LinkedIn-0077B5?style=flat-square&logo=linkedin" alt="LinkedIn">
  </a>
  <a href="https://claude.ai">
    <img src="https://img.shields.io/badge/Powered_by_Claude-6d5dfc?style=flat-square" alt="Powered by Claude">
  </a>
</p>

*Claude Zero to Hero · Expand each section and learn it*

</div>
