<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./assets/header-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="./assets/header-light.svg">
  <img src="./assets/header-dark.svg" width="100%" alt="Aown Abbas, Full Stack Laravel Developer and Agentic AI Engineer. A request reaches an AI agent, which uses vector search, MCP tools and read-only APIs, and every action waits for human approval before it runs.">
</picture>

<p align="center">
  <a href="https://aownabbas.netlify.app"><img src="https://img.shields.io/badge/Portfolio-aownabbas.netlify.app-ffc300?style=flat-square&labelColor=161b22" alt="Portfolio"></a>
  <a href="https://www.linkedin.com/in/aown-abbas-41952b304/"><img src="https://img.shields.io/badge/LinkedIn-Aown_Abbas-0a66c2?style=flat-square&labelColor=161b22" alt="LinkedIn"></a>
  <a href="mailto:codebyaown@gmail.com"><img src="https://img.shields.io/badge/Email-codebyaown@gmail.com-6ee7a8?style=flat-square&labelColor=161b22&logo=gmail&logoColor=white" alt="Email"></a>
  <img src="https://img.shields.io/badge/Open_to-Full_Stack_%26_AI_Engineer_roles-7dd3fc?style=flat-square&labelColor=161b22" alt="Open to Full Stack and AI Engineer roles">
</p>

I've spent four years building production web applications in PHP and Laravel: learning platforms, e-commerce stores, CRMs and a multi-tenant workforce platform. Since 2025 most of my new work has been agentic AI. LLM agents with real tool access, retrieval pipelines, and workflows where the model proposes and a person approves.

The part I care about is the engineering around the model: what an agent is allowed to touch, how it fails safely, and how it fits into a codebase a team already depends on.

## What I work on

<table>
<tr>
<td width="50%" valign="top">

**Agentic AI systems**

- Tool-calling agents behind a policy-enforced, read-only tool registry
- Tool definitions that serve both function calling and **MCP**
- RAG over vector databases, with reranking before the model sees results
- Multi-agent orchestration, with LangGraph and with custom orchestrators
- Human-in-the-loop approval before anything is written
- Model routing, provider fallback and circuit breakers across OpenAI, Claude and local models
- Voice AI: streaming speech-to-text and synthesised replies

</td>
<td width="50%" valign="top">

**Full stack platforms**

- Laravel applications end to end: schema, queues, APIs, admin consoles
- Multi-tenant SaaS, CRMs, e-commerce and payment integrations
- Vue.js, Livewire, React and Next.js front ends
- MySQL, PostgreSQL and Redis, with idempotent background workers
- Python and FastAPI services for the AI side
- WordPress and WooCommerce custom development

</td>
</tr>
</table>

## How I build agents

```mermaid
flowchart LR
    U([User request]) --> A{{"Agent<br/>tool loop"}}
    A <--> R[("Vector search<br/>RAG")]
    A <--> T["Read-only tools<br/>function calling · MCP"]
    A --> P[/"Proposed action<br/>typed and validated"/]
    P --> H{"Human<br/>approval"}
    H -- approved --> W["Authorised write path"]
    H -- rejected --> A
    W --> L[("Audit log")]
```

- **Tool access is enforced in code, not in the prompt.** An allowlist is checked on every call, so a hallucinated tool call can't become a real write.
- **The model proposes and a person approves** anything irreversible or outward-facing.
- **Outputs are structured and validated** against a schema, not prose to be parsed.
- **Retrieved content is treated as data, never as instructions**, which is the first line of defence against prompt injection.
- **Every model vendor sits behind one interface.** Switching providers is configuration, and a circuit breaker moves traffic when one fails.
- **Correctness lives in the database**: unique constraints, row locks and `ON CONFLICT`, not an `if exists()` check two workers can both pass.

## Featured work

<table>
<tr>
<td width="50%" valign="top">

### [AI Lead Generation Platform](https://aownabbas.netlify.app/work/ai-lead-generation-platform/)
A lead lifecycle engine, not a scraper: 13 states, four-tier deduplication, AI research and drafted outreach, and human approval before anything sends. Idempotency enforced in Postgres, around 25 test suites against a real database. *Private repo, case study linked.*

`Python` `FastAPI` `SQLAlchemy` `PostgreSQL` `Redis` `Claude`

</td>
<td width="50%" valign="top">

### [LLM-first Assistant Rebuild](https://aownabbas.netlify.app/work/ai-chat-lead-platform/)
Traced why a customer-facing AI assistant misrouted real questions (regex rules into fixed templates, with the model only as a fallback) and led the rebuild to LLM-first handling with embedding-based semantic retrieval. *Employer work, case study linked.*

`PHP` `WordPress` `WooCommerce` `OpenAI` `Embeddings`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [Multi-tenant Workforce Platform](https://aownabbas.netlify.app/work/shift2go-hrm/)
Rostering, timesheets, leave balances and payroll reporting, with per-company rules and subscription tiers. Live in production. *Client work, case study linked.*

`Laravel` `Vue.js` `MySQL` `Multi-tenant`

</td>
<td width="50%" valign="top">

### [Learning Management Platform](https://aownabbas.netlify.app/work/destinator-university/)
Course catalogue, enrolment, progress tracking and an instructor and admin back office, with checkout through four payment gateways. *Client work, case study linked.*

`Laravel` `Vue.js` `MySQL` `Stripe` `PayPal`

</td>
</tr>
</table>

## Tech stack

**AI and agents**<br>
<img src="https://img.shields.io/badge/Anthropic_Claude-161b22?style=flat-square&logo=claude&logoColor=D97757" alt="Anthropic Claude"> <img src="https://img.shields.io/badge/OpenAI_API-161b22?style=flat-square" alt="OpenAI API"> <img src="https://img.shields.io/badge/MCP-161b22?style=flat-square&logo=modelcontextprotocol&logoColor=white" alt="Model Context Protocol"> <img src="https://img.shields.io/badge/LangGraph-161b22?style=flat-square&logo=langgraph&logoColor=white" alt="LangGraph"> <img src="https://img.shields.io/badge/LangChain-161b22?style=flat-square&logo=langchain&logoColor=white" alt="LangChain"> <img src="https://img.shields.io/badge/Ollama-161b22?style=flat-square&logo=ollama&logoColor=white" alt="Ollama"> <img src="https://img.shields.io/badge/PyTorch-161b22?style=flat-square&logo=pytorch&logoColor=EE4C2C" alt="PyTorch"> <img src="https://img.shields.io/badge/RAG-161b22?style=flat-square" alt="RAG"> <img src="https://img.shields.io/badge/Embeddings-161b22?style=flat-square" alt="Embeddings">

**Backend**<br>
<img src="https://img.shields.io/badge/Python-161b22?style=flat-square&logo=python&logoColor=3776AB" alt="Python"> <img src="https://img.shields.io/badge/FastAPI-161b22?style=flat-square&logo=fastapi&logoColor=009688" alt="FastAPI"> <img src="https://img.shields.io/badge/PHP-161b22?style=flat-square&logo=php&logoColor=777BB4" alt="PHP"> <img src="https://img.shields.io/badge/Laravel-161b22?style=flat-square&logo=laravel&logoColor=FF2D20" alt="Laravel"> <img src="https://img.shields.io/badge/Livewire-161b22?style=flat-square&logo=livewire&logoColor=FB70A9" alt="Livewire"> <img src="https://img.shields.io/badge/Node.js-161b22?style=flat-square&logo=nodedotjs&logoColor=5FA04E" alt="Node.js"> <img src="https://img.shields.io/badge/SQLAlchemy-161b22?style=flat-square&logo=sqlalchemy&logoColor=white" alt="SQLAlchemy">

**Frontend**<br>
<img src="https://img.shields.io/badge/TypeScript-161b22?style=flat-square&logo=typescript&logoColor=3178C6" alt="TypeScript"> <img src="https://img.shields.io/badge/JavaScript-161b22?style=flat-square&logo=javascript&logoColor=F7DF1E" alt="JavaScript"> <img src="https://img.shields.io/badge/React-161b22?style=flat-square&logo=react&logoColor=61DAFB" alt="React"> <img src="https://img.shields.io/badge/Next.js-161b22?style=flat-square&logo=nextdotjs&logoColor=white" alt="Next.js"> <img src="https://img.shields.io/badge/Vue.js-161b22?style=flat-square&logo=vuedotjs&logoColor=4FC08D" alt="Vue.js"> <img src="https://img.shields.io/badge/Tailwind_CSS-161b22?style=flat-square&logo=tailwindcss&logoColor=06B6D4" alt="Tailwind CSS">

**Data and retrieval**<br>
<img src="https://img.shields.io/badge/PostgreSQL-161b22?style=flat-square&logo=postgresql&logoColor=4169E1" alt="PostgreSQL"> <img src="https://img.shields.io/badge/pgvector-161b22?style=flat-square&logo=postgresql&logoColor=white" alt="pgvector"> <img src="https://img.shields.io/badge/MySQL-161b22?style=flat-square&logo=mysql&logoColor=4479A1" alt="MySQL"> <img src="https://img.shields.io/badge/Redis-161b22?style=flat-square&logo=redis&logoColor=FF4438" alt="Redis"> <img src="https://img.shields.io/badge/ChromaDB-161b22?style=flat-square" alt="ChromaDB"> <img src="https://img.shields.io/badge/Qdrant-161b22?style=flat-square&logo=qdrant&logoColor=DC244C" alt="Qdrant">

**Platforms and tools**<br>
<img src="https://img.shields.io/badge/Docker-161b22?style=flat-square&logo=docker&logoColor=2496ED" alt="Docker"> <img src="https://img.shields.io/badge/Git-161b22?style=flat-square&logo=git&logoColor=F05032" alt="Git"> <img src="https://img.shields.io/badge/WordPress-161b22?style=flat-square&logo=wordpress&logoColor=21759B" alt="WordPress"> <img src="https://img.shields.io/badge/WooCommerce-161b22?style=flat-square&logo=woocommerce&logoColor=96588A" alt="WooCommerce"> <img src="https://img.shields.io/badge/Vercel-161b22?style=flat-square&logo=vercel&logoColor=white" alt="Vercel"> <img src="https://img.shields.io/badge/Netlify-161b22?style=flat-square&logo=netlify&logoColor=00C7B7" alt="Netlify">

## Right now

- Full stack and AI engineering at **Carbon Reprographics** (remote, US)
- Building the **AI lead generation platform** above
- Open to **Full Stack Engineer** and **Agentic AI Engineer** roles, remote or relocating for the right team

<p align="center"><sub>Case studies, screenshots and architecture for all of the above at <a href="https://aownabbas.netlify.app">aownabbas.netlify.app</a></sub></p>
