# Task: AI Coding Agent Landscape Report (February 2026)

Research and produce a comprehensive landscape report on AI-powered coding agents and developer tools as of **February 2026**. Use `web_search` extensively to find **current** (2025-2026) information. Write all findings to markdown files in `report/`.

**CRITICAL**: Today is February 2026. Your training data may be outdated. Use `web_search` for ALL factual claims — pricing, star counts, model names, benchmark scores. Do NOT rely on internal knowledge alone. If a search returns no results for a 2026 query, try 2025.

**Output structure:**
```
report/
  00-executive-summary.md
  01-open-source-agents.md
  02-commercial-agents.md
  03-benchmarks-and-evals.md
  04-architecture-patterns.md
  05-model-providers.md
  06-developer-experience.md
  07-market-analysis.md
  08-recommendations.md
```

---

## 1. Open-Source Coding Agents (researcher-a)

Research each of the following open-source coding agents. For **each**, find:
- GitHub repo URL, star count, license, latest release date
- Architecture (CLI, IDE plugin, web, agentic loop style)
- Which LLM providers/models it supports
- Key differentiating features
- Known limitations or community complaints
- Recent notable changes (last 3 months)

**Agents to cover:**
- Aider
- Open Interpreter
- SWE-agent / SWE-bench
- Mentat
- Continue.dev
- Tabby (TabbyML)
- Sweep AI
- Devon (Cognition open-source components if any)
- GPT-Engineer
- Cline (formerly Claude Dev)

Write findings to `report/01-open-source-agents.md` with a comparison table at the end. Target: 800-1500 words.

---

## 2. Commercial Coding Agents (researcher-b)

Research each commercial/proprietary coding agent or AI coding tool. For **each**, find:
- Company, pricing model, free tier availability
- Supported IDEs/platforms
- Which models power it (and whether users can choose)
- Key features (auto-complete, chat, agentic tasks, multi-file edits)
- Enterprise features (SSO, audit logs, on-prem)
- Recent product launches or pivots (last 6 months)

**Tools to cover:**
- GitHub Copilot (including Copilot Workspace and Agent mode)
- Cursor
- Windsurf (Codeium)
- Claude Code (Anthropic)
- Amazon Q Developer (formerly CodeWhisperer)
- Google Gemini Code Assist / Jules
- JetBrains AI Assistant
- Sourcegraph Cody
- Tabnine
- Replit Agent
- Devin (Cognition)
- Augment Code
- Poolside AI

Write findings to `report/02-commercial-agents.md` with a pricing comparison table. Target: 800-1500 words.

---

## 3. Benchmarks & Evaluations (researcher-c)

Research the current state of coding agent benchmarks and evaluation frameworks:

- **SWE-bench**: Latest leaderboard standings, what the top 5 agents score, methodology criticisms
- **HumanEval / MBPP / MultiPL-E**: Which models lead, saturation concerns
- **Aider benchmark**: Methodology, polyglot leaderboard, how it differs from SWE-bench
- **LiveCodeBench**: What it measures, latest results
- **BigCodeBench**: Scope and recent results
- **CanAICode**: Coverage and relevance
- **CyberSecEval / CWE benchmarks**: Security-focused code generation evals
- **Real-world metrics**: Any published data on productivity gains (e.g., Google, Microsoft, Shopify internal studies)

For each benchmark, note: what it measures, known limitations, whether it's being gamed, and the top-performing models/agents.

Write to `report/03-benchmarks-and-evals.md`. Target: 800-1500 words.

---

## 4. Architecture Patterns (researcher-a)

Research and document the dominant architecture patterns used in coding agents:

- **ReAct loop** vs **Plan-then-Execute** vs **Tree-of-Thought** — which agents use which?
- **Tool use patterns**: File I/O, bash execution, LSP integration, browser use
- **Context engineering**: How do agents handle long contexts? (compaction, RAG, sliding window, hierarchical summarization)
- **Multi-agent / swarm patterns**: Orchestrator-worker, debate, ensemble, review chains
- **Sandboxing approaches**: Docker, E2B, Firecracker, modal, local process isolation
- **Memory systems**: Cross-session learning, vector stores, knowledge graphs
- **Model routing**: When to use cheap vs expensive models, cascading

Search for recent blog posts, papers, and talks from agent builders. Cite sources.

Write to `report/04-architecture-patterns.md`. Target: 800-1500 words.

---

## 5. Model Providers & Capabilities (researcher-b)

Research the current LLM landscape specifically for code generation:

- **Anthropic Claude** (Opus 4.6, Sonnet 4.5, Haiku 4.5): Code capabilities, extended thinking, tool use, pricing
- **OpenAI** (GPT-4.5, o3, o4-mini): Code capabilities, pricing, function calling
- **Google** (Gemini 2.5 Pro/Flash): Code capabilities, long context, pricing
- **Meta Llama** (Llama 4): Open-weight code models, fine-tuning ecosystem
- **DeepSeek** (V3, R1): Pricing, capabilities, controversy
- **Mistral** (Large, Codestral): European alternative, on-prem appeal
- **Qwen** (Qwen 3, Coder variants): Chinese open-weight models
- **Smaller specialists**: StarCoder 2, Phind, WizardCoder, CodeGemma

For each: context window, pricing per 1M tokens (input/output), code benchmark scores, unique strengths.

Write to `report/05-model-providers.md` with a comparison matrix. Target: 800-1500 words.

---

## 6. Developer Experience Research (researcher-c)

Research developer sentiment and UX patterns across AI coding tools:

- Search for **developer surveys** about AI coding tools (Stack Overflow 2025, JetBrains 2025, GitHub surveys)
- Search for **Reddit threads** and **HN discussions** about coding agent pain points
- Find **adoption statistics**: What % of developers use AI tools? Which tools are most popular?
- Research **common complaints**: hallucinations, context loss, breaking changes, trust issues
- Find **success stories**: Teams that measurably improved velocity with AI agents
- Research **workflow patterns**: How do developers integrate agents into their workflow? (pair programming, review, generation, debugging)

Write to `report/06-developer-experience.md`. Target: 800-1500 words.

---

## 7. Market Analysis (researcher-a)

Research the business/market side:

- **Funding rounds**: Which AI coding companies raised recently? Valuations?
- **Acquisitions**: Any M&A activity in the coding agent space?
- **Market size estimates**: TAM/SAM for AI developer tools (analyst reports, press coverage)
- **Enterprise adoption trends**: Which Fortune 500s are deploying coding agents?
- **Regulatory landscape**: Any emerging regulations on AI-generated code? (EU AI Act impact, export controls)
- **Open source vs commercial dynamics**: Is the gap narrowing or widening?

Write to `report/07-market-analysis.md`. Target: 800-1500 words.

---

## 8. Executive Summary & Recommendations (synthesizer)

After all research sections are complete, synthesize into:

- `report/00-executive-summary.md`: 1-page summary of key findings, trends, and surprises
- `report/08-recommendations.md`: Actionable recommendations for:
  - A startup building a coding agent (what to differentiate on)
  - An enterprise evaluating coding tools (what to look for)
  - An open-source contributor (where to focus effort)

This section depends on ALL other sections being complete first.

---

## Research Guidelines

- **Use `web_search` for every factual claim.** Do not rely on training data alone — search to verify and find current information.
- **Cite sources**: Include URLs for key claims.
- **Be specific**: Include actual numbers (star counts, pricing, benchmark scores) not vague statements.
- **Acknowledge uncertainty**: If info is conflicting or unavailable, say so.
- **Date-stamp findings**: The current date is February 2026. Note when information was retrieved.
- **Target depth**: Each section should be 800-1500 words with data tables where appropriate.
- **Write the full content to the target file**. Do NOT leave empty files or placeholder text. Every target file must contain the complete section.
