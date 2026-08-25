# Learning Plan: Building Autonomous Agents for Personal Research and Use

## Intro

This is a resource-discovery catalog for learning to design and build **LLM-powered autonomous
agents** — systems that plan, call tools, browse the web, remember context across turns, and act
toward a goal with minimal supervision. It is deliberately broad: foundational concepts (ReAct,
planning loops, tool/function calling), memory and retrieval (RAG, vector stores, memory
architectures), frameworks/SDKs across the whole ecosystem (OpenAI, Anthropic, LangChain/
LangGraph, CrewAI, AutoGen/Microsoft Agent Framework, LlamaIndex, Hugging Face smolagents,
Semantic Kernel, browser-automation tooling), evaluation and benchmarking, safety/guardrails, and
the community layer (courses, papers, repos, forums, YouTube/podcasts). Every item below lists a
real URL, a one-line description, and whether it's free or paid. This document is a **plan**, not
a tutorial — a future agent will use it to actually build notebooks, exercises, and docs.

A suggested rough learning order (beginner → intermediate → advanced) is included at the very end.

---

## 1. Foundational Concept Resources

What "agent" means in the LLM context, the ReAct pattern, planning/reasoning loops, and
tool-calling/function-calling.

- **ReAct paper — "ReAct: Synergizing Reasoning and Acting in Language Models"** — https://arxiv.org/abs/2210.03629 — The original paper defining the Thought→Action→Observation loop that underlies almost every modern agent; free.
- **Google Research blog on ReAct** — https://research.google/blog/react-synergizing-reasoning-and-acting-in-language-models/ — Plain-language summary of the ReAct paper from the authors' lab; free.
- **ysymyth/ReAct (official code)** — https://github.com/ysymyth/ReAct — Official implementation/prompts used in the ReAct paper, useful for seeing exact prompt formats; free.
- **Arize AI — "Keys to Understanding ReAct"** — https://arize.com/blog/keys-to-understanding-react/ — Practitioner explainer connecting ReAct theory to production agent debugging; free.
- **Anthropic — "Building Effective Agents"** — https://www.anthropic.com/engineering/building-effective-agents — Foundational engineering post distinguishing "workflows" from "agents," with concrete patterns (prompt chaining, routing, parallelization, orchestrator-workers, evaluator-optimizer) and when to use an agent at all; free.
- **Anthropic — "Writing Tools for Agents"** — https://www.anthropic.com/engineering/writing-tools-for-agents — Practical guidance on designing the "agent-computer interface" (tool naming, schemas, error messages); free.
- **Anthropic — "Effective Context Engineering for AI Agents"** — https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents — How to manage what goes into an agent's context window over a long task; free.
- **OpenAI — "A Practical Guide to Building Agents" (34-page PDF)** — https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/ — Free official guide covering agent foundations (model + tools + instructions), when to use agents, single- vs multi-agent orchestration, and guardrails; free.
- **OpenAI — Function calling guide** — https://developers.openai.com/api/docs/guides/function-calling — Official reference on the request/response loop for tool/function calling; free.
- **OpenAI — "New tools for building agents" announcement** — https://openai.com/index/new-tools-for-building-agents/ — Overview of Responses API, built-in tools, and Agents SDK; free.
- **Anthropic — Tool use overview (Claude docs)** — https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview — Official Claude tool-calling documentation; free.
- **Anthropic — "Advanced Tool Use"** — https://www.anthropic.com/engineering/advanced-tool-use — Deeper patterns for tool design at scale (parallel tools, tool search, code execution with tools); free.
- **Simon Willison — definition and writing on agents ("LLMs calling tools in a loop")** — https://simonwillison.net/tags/ai-agents/ — An opinionated, continuously-updated stream of practitioner posts defining and dissecting what "agent" really means; free.
- **Simon Willison — "The lethal trifecta for AI agents"** — https://simonw.substack.com/p/the-lethal-trifecta-for-ai-agents — Core safety mental model: private data + untrusted content + external communication = danger; free.
- **Model Context Protocol (MCP) announcement — Anthropic** — https://www.anthropic.com/news/model-context-protocol — The open standard ("USB-C for AI") for connecting agents to tools/data/services via a client-server protocol; free.
- **Andrew Ng — Four Agentic Design Patterns thread** — https://www.linkedin.com/posts/andrewyng_announcing-my-new-course-agentic-ai-building-activity-7381380126317404160-wW75 and course summary at https://learn.deeplearning.ai/courses/agentic-ai/lesson/rm9bg7/agentic-design-patterns — Reflection, Tool Use, Planning, Multi-agent Collaboration as the four core building blocks of agentic systems; free to read the framing.

---

## 2. Best Courses Covering Agent-Building Specifically

University courses, MOOC-style courses, and well-known practitioner short courses.

### University-level

- **UC Berkeley CS294/194-196 — "Large Language Model Agents" (Fall 2024)** — http://rdi.berkeley.edu/llm-agents/f24 — Taught by Dawn Song with Xinyun Chen; covers LLM fundamentals, reasoning/planning, tool use, RAG, code generation, multimodal agents, robotics, evaluation, safety/ethics; lecture videos on YouTube playlist https://www.youtube.com/playlist?list=PLS01nW3RtgorL3AW8REU9nGkzhvtn6Egn; free (audit via public materials/YouTube).
- **UC Berkeley CS294/194-280 — "Advanced Large Language Model Agents" (Spring 2025)** — http://rdi.berkeley.edu/adv-llm-agents/sp25 — Follow-on course, deeper on reasoning, agentic workflows, tool use, code verification, theorem proving; free (public materials).

### MOOC / practitioner short courses (mostly free)

- **DeepLearning.AI — "Agentic AI" (Andrew Ng)** — https://www.deeplearning.ai/courses/agentic-ai — Flagship conceptual course (~10h) on reflection, tool use, planning, multi-agent collaboration; free during platform access.
- **DeepLearning.AI — "AI Agents in LangGraph"** — https://www.deeplearning.ai/courses/ai-agents-in-langgraph — Build an agent from scratch in Python, then rebuild in LangGraph; free.
- **DeepLearning.AI — "Multi AI Agent Systems with crewAI"** — https://www.deeplearning.ai/courses/multi-ai-agent-systems-with-crewai — Organizing teams of role-based agents for multi-step business tasks; free.
- **DeepLearning.AI — "Practical Multi AI Agents and Advanced Use Cases with crewAI"** — https://www.deeplearning.ai/courses/practical-multi-ai-agents-and-advanced-use-cases-with-crewai — Advanced crewAI patterns (hierarchical crews, planning); free.
- **DeepLearning.AI — "Building AI Browser Agents"** — https://www.deeplearning.ai/courses/building-ai-browser-agents — Building agents that operate a web browser; free.
- **DeepLearning.AI — "Governing AI Agents"** — https://www.deeplearning.ai/courses/governing-ai-agents — Governance/safety-focused short course; free.
- **DeepLearning.AI — "A2A: The Agent2Agent Protocol"** — https://www.deeplearning.ai/courses/a2a-the-agent2agent-protocol — Interoperability standard for agent-to-agent communication; free.
- **DeepLearning.AI — "Agent Skills with Anthropic"** — https://www.deeplearning.ai/courses/agent-skills-with-anthropic — Building reusable "Skills" for Claude-based agents; free.
- **DeepLearning.AI — "Agent Memory: Building Memory-Aware Agents"** — https://www.deeplearning.ai/courses/agent-memory-building-memory-aware-agents — Dedicated short course on memory design for agents; free.
- **DeepLearning.AI — "AI Agentic Design Patterns with AutoGen"** — https://www.deeplearning.ai/courses/ai-agentic-design-patterns-with-autogen — Design patterns taught through Microsoft's AutoGen framework; free.
- **Hugging Face — Agents Course** — https://huggingface.co/learn/agents-course/en/unit0/introduction (repo: https://github.com/huggingface/agents-course) — 4-unit interactive course covering agent fundamentals, smolagents, LlamaIndex agents, and a final project; free, with a free certification.
- **Microsoft — "AI Agents for Beginners"** — https://github.com/microsoft/ai-agents-for-beginners (site: https://microsoft.github.io/ai-agents-for-beginners/01-intro-to-ai-agents/) — 10+ lesson open-source course with notebooks, using GitHub Models for free API access; free.
- **freeCodeCamp — "AI Agents For Beginners" (YouTube, ~3h)** — https://www.freecodecamp.org/news/ai-agents-for-beginners/ — Full video course from LLM fundamentals to multi-agent systems; free.
- **freeCodeCamp — "Agentic AI using LangGraph" (~24h)** — https://www.freecodecamp.org/news/agentic-ai-using-langgraph-build-ai-agents-automate-workflows/ — Long-form production-oriented LangGraph course; free.
- **freeCodeCamp — "Learn Python and Build Autonomous Agents" (~6h)** — https://www.freecodecamp.org/news/learn-python-and-build-autonomous-agents/ — Starts with Python basics, ends with agent-building; free.
- **LangChain Academy — course catalog** — https://academy.langchain.com/ — Official LangChain training hub; includes "Introduction to LangChain," "Building Reliable Agents," "Intro to Building Agents," "Intro to LangSmith"; most content free.
- **Anthropic Academy — "Building with the Claude API"** — https://academy.claude.com/courses/building-with-the-claude-api — Official Anthropic course covering tool use, RAG, MCP, and agent architectures; free.
- **Anthropic Academy — "Introduction to Agent Skills"** — https://anthropic.skilljar.com/introduction-to-agent-skills — Building/sharing reusable Skills for Claude Code agents; free.

### Paid (label clearly as paid; call out only the exceptionally well-regarded)

- **Coursera — "Agentic AI Engineering Specialization"** — https://www.coursera.org/specializations/agentic-ai-engineering — Production-ready agents with LangChain, LangGraph, and MCP; **paid** (certificate), audit/financial aid may be available.
- **Coursera — "Building AI Agents and Agentic Workflows Specialization"** — https://www.coursera.org/specializations/building-ai-agents-and-agentic-workflows — Covers LangGraph, CrewAI, BeeAI, and AG2 (AutoGen) with cloud labs; **paid**.
- **Coursera — "Hands-on Agentic AI: Building Intelligent Agents"** — https://www.coursera.org/specializations/hands-on-agentic-ai-building-intelligent-agents — Broad hands-on specialization; **paid**.
- **DataCamp — "AI Agents with Hugging Face smolagents"** — https://www.datacamp.com/courses/ai-agents-with-hugging-face-smolagents — Focused hands-on course on the smolagents library; **paid** (DataCamp subscription), some free preview.
- **DataCamp — "Retrieval Augmented Generation (RAG) with LangChain"** — https://www.datacamp.com/courses/retrieval-augmented-generation-rag-with-langchain — Well-regarded structured RAG course; **paid**.
- **Udemy — "LangChain — Develop AI Agents with LangChain & LangGraph"** — https://www.udemy.com/topic/ai-agents/ (topic hub; search this exact title) — Popular beginner-to-advanced bestseller with large enrollment; **paid** (frequent deep discounts).
- **Zero To Mastery — "AI Agents Bootcamp"** — https://zerotomastery.io/courses/ai-agents-bootcamp/ — Project-driven bootcamp-style course; **paid**.

---

## 3. Free Courses and Structured Learning Paths

(Overlaps intentionally with §2 but focused specifically on *paths*, not single courses.)

- **Hugging Face Agents Course (4-unit path)** — https://huggingface.co/learn/agents-course/en/unit0/introduction — See §2; the clearest single free end-to-end path from theory to a certified final project; free.
- **Microsoft "AI Agents for Beginners" (GitHub Study Guide)** — https://github.com/microsoft/ai-agents-for-beginners/blob/main/STUDY_GUIDE.md — Structured week-by-week study guide accompanying the lessons; free.
- **Berkeley LLM Agents MOOC notes/community repo** — https://github.com/xianminx/mooc-cs294-llm-agents — Community-run companion to the Berkeley course for self-paced learners; free.
- **LangChain Academy learning bundle — "Intro to Building Agents"** — https://academy.langchain.com/bundles/intro-to-building-agents — Sequenced bundle: `create_agent`, tools, MCP, streaming, structured outputs; free.
- **Medium — "13 Free Courses to Build Agentic Systems in 2025"** — https://medium.com/magic-ai/13-free-courses-to-build-agentic-systems-in-2025-updated-for-august-f33add04d364 — Continuously updated roundup aggregating free options across providers; free (article itself).
- **DeepLearning.AI community thread — recommended order for agent short courses** — https://community.deeplearning.ai/t/recommended-order-to-learn-on-ai-agent-short-courses/788174 — Crowd-sourced sequencing advice across the DLAI agent-course catalog; free.

---

## 4. Foundational Papers and Blog Posts

Core agent concepts: ReAct, Reflexion, Toolformer, multi-agent debate/orchestration, memory
architectures.

- **ReAct: Synergizing Reasoning and Acting in Language Models** — https://arxiv.org/abs/2210.03629 — Foundational Thought/Action/Observation loop paper (Yao et al., 2022); free.
- **Reflexion: Language Agents with Verbal Reinforcement Learning** — https://arxiv.org/abs/2303.11366 (code: https://github.com/noahshinn/reflexion) — Agents self-critique via verbal feedback stored in episodic memory instead of weight updates; reports 91% pass@1 on HumanEval; free.
- **Toolformer: Language Models Can Teach Themselves to Use Tools** — https://arxiv.org/abs/2302.04761 — Self-supervised method for a model to learn which API to call, when, and with what arguments; free.
- **Improving Factuality and Reasoning in Language Models through Multiagent Debate** — https://composable-models.github.io/llm_debate/ — Canonical multi-agent debate paper: multiple LLM instances debate and revise answers over rounds; free.
- **"Should we be going MAD?" (Multi-Agent Debate benchmarking)** — https://proceedings.mlr.press/v235/smit24a.html — Benchmark-oriented critique/evaluation of multi-agent debate protocols; free (proceedings).
- **Multi-Agent Collaboration via Evolving Orchestration** — https://arxiv.org/abs/2505.19591 — RL-trained centralized orchestrator that dynamically sequences which agent speaks; free.
- **awesome-multi-agent-papers (curated list)** — https://github.com/kyegomez/awesome-multi-agent-papers — Curated bibliography specifically for multi-agent LLM papers; free.
- **A Survey on Large Language Model based Autonomous Agents** — https://arxiv.org/abs/2308.11432 (companion repo https://github.com/paitesanshi/llm-agent-survey) — Broad, frequently-cited survey of agent construction, applications, and evaluation; free.
- **Large Language Model Agent: A Survey on Methodology, Applications and Challenges** — https://arxiv.org/abs/2503.21460 — 329-paper taxonomy of architecture, collaboration, applications, challenges; free.
- **A Survey on Evaluation of LLM-based Agents** — https://arxiv.org/html/2503.16416v2 — Dedicated survey of agent evaluation methods, benchmarks, frameworks; free.
- **Large Language Model Based Multi-Agents: A Survey of Progress and Challenges** — https://www.ijcai.org/proceedings/2024/890 — IJCAI 2024 survey of multi-agent LLM systems, communication, skill development; free.
- **WooooDyy/LLM-Agent-Paper-List** — https://github.com/WooooDyy/LLM-Agent-Paper-List — One of the most comprehensive continuously-updated agent-paper trackers; free.
- **Redis — "AI Agent Memory: Building Stateful Systems"** — https://redis.io/blog/ai-agent-memory-stateful-systems/ — Practitioner write-up on short-term vs long-term memory architecture with vector stores; free.
- **Redis — "Long-Term Memory Architectures for AI Agents"** — https://redis.io/blog/long-term-memory-architectures-ai-agents/ — Deeper dive on archival memory design; free.
- **Atlan — "Agent Memory Architectures" / "How to Choose an AI Agent Memory Architecture"** — https://atlan.com/know/agent-memory-architectures/ and https://atlan.com/know/how-to-choose-ai-agent-memory-architecture/ — Practical taxonomy of memory patterns (monolithic context, context+retrieval, tiered memory); free.
- **Machine Learning Mastery — "5 Architectural Patterns for Persistent Memory and State in AI Agents"** — https://machinelearningmastery.com/5-architectural-patterns-for-persistent-memory-and-state-in-ai-agents/ — Concrete pattern catalog (vector, graph, episodic, hybrid); free.
- **IBM Think — "What is AI Agent Memory?"** — https://www.ibm.com/think/topics/ai-agent-memory — Accessible primer distinguishing short-term/long-term/episodic/semantic memory; free.

---

## 5. Hands-on Labs, Notebooks, and Sandboxes

Runnable environments for building a first agent, free-tier experimentation spaces.

- **Google Colab (free T4 GPU tier)** — https://colab.research.google.com/ — Free notebook environment; used by most "build your first agent in 15 minutes" tutorials; free.
- **"AI Agent Tutorial From Scratch in 15 Minutes" (Colab notebook)** — https://www.youtube.com/watch?v=RPI8-ZyVhzU — Builds an agent from scratch on Colab's free T4 GPU using Qwen2.5, Ollama, LangChain, LangGraph; free.
- **Pinecone — LangChain Handbook agents notebook** — https://colab.research.google.com/github/pinecone-io/examples/blob/master/learn/generation/langchain/handbook/06-langchain-agents.ipynb — Runnable Colab notebook walking through LangChain agent construction; free.
- **50 Colab Notebooks for AI Agents and Agentic Projects (roundup)** — https://www.linkedin.com/pulse/50-colab-notebooks-ai-agents-agentic-projects-asif-razzaq-abygc — Curated list of 50 free runnable notebooks across agent use cases; free.
- **OpenAI Cookbook — "Orchestrating Agents: Routines and Handoffs"** — https://github.com/openai/openai-cookbook/blob/main/examples/Orchestrating_agents.ipynb — Runnable notebook demonstrating lightweight multi-agent handoff patterns; free (requires OpenAI API key, paid usage).
- **OpenAI Cookbook — Agents SDK examples folder** — https://github.com/openai/openai-agents-python/tree/main/examples — Parallel agents, context personalization, dispute-resolution agent examples; free (code), paid API usage.
- **OpenAI Developers Cookbook — Agents topic hub** — https://developers.openai.com/cookbook/topic/agents — Organized index of all agent-related cookbook notebooks; free.
- **E2B (e2b-dev/E2B)** — https://github.com/e2b-dev/e2b (docs: https://docs.e2b.dev/use-cases/coding-agents) — Open-source cloud sandbox for letting agents safely execute code; free tier + paid cloud plans.
- **Hugging Face Spaces — GAIA benchmark leaderboard/space** — https://huggingface.co/spaces/gaia-benchmark/leaderboard — Live leaderboard you can also use to sanity-check your own agent's tool-use ability; free.
- **Hugging Face smolagents quickstart / "agents that think in code"** — https://huggingface.co/docs/smolagents/en/index — Minimal, few-lines-of-code way to spin up a working `CodeAgent` in a notebook; free (HF Inference free tier available).

---

## 6. GitHub Repos Worth Studying or Cloning

Popular open-source frameworks, from-scratch minimal implementations, awesome-lists,
multi-agent examples, browsing/tool-use agents.

### Minimal / from-scratch agent loops
- **ysymyth/ReAct** — https://github.com/ysymyth/ReAct — Original ReAct paper code; the cleanest place to see a bare Thought/Action/Observation loop; free.
- **yoheinakajima/babyagi** (and successors `babyagi3`, `babyagi-2o`) — https://github.com/yoheinakajima/babyagi — Minimal task-loop agent: create → prioritize → execute tasks, backed by memory; the classic ~30-line "agent from scratch" reference; free.
- **noahshinn/reflexion** — https://github.com/noahshinn/reflexion — Reference implementation of the Reflexion self-reflection loop; free.

### General-purpose frameworks (open source)
- **significant-gravitas/AutoGPT** — https://github.com/significant-gravitas/autogpt — One of the earliest and most famous general autonomous-agent projects; free.
- **microsoft/autogen** — https://github.com/microsoft/autogen — Multi-agent conversation framework from Microsoft (community/Discord support link in repo); free.
- **microsoft/agent-framework** — https://github.com/microsoft/agent-framework — Successor to AutoGen/Semantic Kernel; production-grade multi-language (.NET/Python) agent framework with A2A/MCP interoperability; free.
- **microsoft/semantic-kernel** — https://github.com/microsoft/semantic-kernel — Model-agnostic SDK for building/orchestrating agents across .NET, Python, Java; free.
- **langchain-ai/langgraph** (org: https://github.com/orgs/langchain-ai/repositories) — Graph/state-machine based agent orchestration, the most common "production agent" framework in 2025 roundups; free (open source), paid LangSmith/LangGraph Platform tiers exist.
- **crewAI (crewAIInc/crewAI)** — referenced via https://www.deeplearning.ai/courses/multi-ai-agent-systems-with-crewai — Role-based "crews" of agents; free core, paid Enterprise tier.
- **huggingface/smolagents** — https://github.com/huggingface/smolagents — Barebones library where agents "think in code"; model-agnostic via LiteLLM; free.
- **huggingface/agents-course** — https://github.com/huggingface/agents-course — Source repo for the HF Agents Course, good to clone for exercises; free.
- **run-llama/llama_index** — https://github.com/run-llama/llama_index — LlamaIndex core repo; `FunctionAgent`/`ReActAgent`/`AgentWorkflow` for RAG-centric agents; free.
- **SuperAGI (TransformerOptimus/SuperAGI)** referenced in https://github.com/Jenqyang/Awesome-AI-Agents — Open-source autonomous agent framework with a GUI and tool marketplace; free.
- **PraisonAI** — referenced in https://github.com/aloth/awesome-ai-agents — Multi-agent framework with MCP integration and workflow automation; free.
- **Dify** — referenced in https://github.com/aloth/awesome-ai-agents — Open-source visual LLM app / agent-workflow builder platform; free (self-host), paid cloud.

### Browser / tool-use agents
- **microsoft/playwright** — https://github.com/microsoft/playwright — The underlying browser automation engine most agent browsing tools sit on top of; has an MCP server for structured, screenshot-free agent control; free.
- **browser-use/browser-use** — https://github.com/browser-use/browser-use — Python library that turns any LLM into a web-browsing agent (click, type, fill forms); MIT license; free.
- **Skyvern-AI/skyvern** — https://github.com/skyvern-ai/skyvern — LLM + computer-vision browser automation, works on unseen websites; Python/TS SDK, MCP server, CLI; open-source core (AGPL-3.0), paid managed cloud for advanced anti-bot features.
- **steel-dev/awesome-web-agents** — https://github.com/steel-dev/awesome-web-agents — Curated list specifically of web/browsing agent projects; free.
- **vercel-labs/agent-browser** — https://github.com/vercel-labs/agent-browser — CLI-driven browser automation tool built for agent workflows (screenshots, recording, snapshotting); free.

### Memory / RAG tooling repos
- **mem0ai/mem0** — https://github.com/mem0ai/mem0 — "Universal memory layer for AI agents"; persistent, personalized memory SDKs (Python/TS); free core, paid hosted platform.
- **getzep/zep** — https://github.com/getzep/zep — Memory platform building a temporal knowledge graph from agent/user interactions; free core, paid hosted platform.
- **getzep/graphiti** — https://github.com/getzep/graphiti — The temporal context-graph engine underpinning Zep; free.
- **NirDiamant/Agent_Memory_Techniques** — https://github.com/NirDiamant/Agent_Memory_Techniques — Collection of practical memory-implementation techniques and code; free.

### Coding-agent sandboxes
- **e2b-dev/E2B** — https://github.com/e2b-dev/e2b — Secure cloud sandbox SDK used by many coding agents to execute LLM-generated code; free tier + paid.

### Awesome-lists / curated indexes
- **e2b-dev/awesome-ai-agents** — https://github.com/e2b-dev/awesome-ai-agents — Curated list of autonomous agents and related resources; free.
- **Jenqyang/Awesome-AI-Agents** — https://github.com/Jenqyang/Awesome-AI-Agents — Collection of autonomous agent projects/frameworks including AutoGen, SuperAGI; free.
- **aloth/awesome-ai-agents** — https://github.com/aloth/awesome-ai-agents — Broad list of frameworks, tools, platforms, papers (AG2, AgentScope, Agno, AutoGen, etc.); free.
- **slavakurilyak/awesome-ai-agents** — https://github.com/slavakurilyak/awesome-ai-agents — 200+ curated agentic AI resources; free.
- **kaushikb11/awesome-llm-agents** — https://github.com/kaushikb11/awesome-llm-agents — Highly-starred curated list of LLM agent frameworks; free.
- **kyrolabs/awesome-langchain** — https://github.com/kyrolabs/awesome-langchain — Curated list of LangChain ecosystem tools/projects; free.
- **Shubhamsaboo/awesome-llm-apps** — https://github.com/Shubhamsaboo/awesome-llm-apps — 100+ ready-to-run agent and RAG app examples (research agent, browser MCP agent, travel agent, chess agent, etc.) to clone and study; free.
- **ashishpatel26/500-AI-Agents-Projects** — https://github.com/ashishpatel26/500-AI-Agents-Projects — Large index of real-world agent project examples across industries; free.
- **philschmid/ai-agent-benchmark-compendium** — https://github.com/philschmid/ai-agent-benchmark-compendium — Curated compendium of agent benchmarks (see §10); free.
- **VoltAgent/awesome-ai-agent-papers** — https://github.com/VoltAgent/awesome-ai-agent-papers — Curated academic paper list specifically for agents; free.
- **THUDM/AgentBench** — https://github.com/THUDM/AgentBench — Cross-domain agent benchmark repo (also useful as a study reference for eval design); free.

---

## 7. Agent Frameworks/SDKs Across the Ecosystem

Tool-agnostic overview: orchestration frameworks, memory/vector-store tooling, browser-automation
tooling. Open-source and commercial noted explicitly.

### General orchestration frameworks
| Framework | Link | Notes | Free/Paid |
|---|---|---|---|
| OpenAI Agents SDK | https://openai.github.io/openai-agents-python/ | Official OpenAI SDK: function tools, MCP support, handoffs | Free SDK, paid model usage |
| Anthropic Claude tool-use / Agent Skills | https://platform.claude.com/docs/en/agents-and-tools/tool-use/overview | Native Claude tool-calling + reusable "Skills" | Free docs, paid model usage |
| LangChain / LangGraph | https://docs.langchain.com/oss/python/langchain/agents , https://langchain-ai.github.io/langgraph/ | Most widely adopted graph/state-machine orchestration for production agents | Free core, paid LangSmith/Platform |
| CrewAI | https://www.deeplearning.ai/courses/multi-ai-agent-systems-with-crewai (project) | Role-based "crews" for fast multi-agent prototyping | Free core, paid Enterprise |
| Microsoft AutoGen / Agent Framework | https://github.com/microsoft/autogen , https://github.com/microsoft/agent-framework | Conversational multi-agent research framework and its production successor | Free, open source |
| Microsoft Semantic Kernel | https://github.com/microsoft/semantic-kernel | Model-agnostic SDK for .NET/Python/Java agent orchestration | Free, open source |
| LlamaIndex (agents + AgentWorkflow) | https://developers.llamaindex.ai/python/framework/understanding/agent/ | RAG-centric agent framework; FunctionAgent/ReActAgent/multi-agent workflows | Free core, paid LlamaCloud |
| Hugging Face smolagents | https://github.com/huggingface/smolagents | Minimal "agents that think in code" library | Free |
| Dify | (see §6) | Visual no-code/low-code agent & LLM app builder | Free self-host, paid cloud |
| PraisonAI | (see §6) | Multi-agent framework with MCP integration | Free |
| AgentScope (Alibaba) | referenced via https://github.com/aloth/awesome-ai-agents | Production-oriented multi-agent framework | Free, open source |

### Memory / vector-store tooling
| Tool | Link | Notes | Free/Paid |
|---|---|---|---|
| Mem0 | https://github.com/mem0ai/mem0 | Universal memory layer, persistent personalized memory | Free core, paid platform |
| Zep + Graphiti | https://github.com/getzep/zep , https://github.com/getzep/graphiti | Temporal knowledge-graph memory | Free core, paid platform |
| Chroma | https://www.trychroma.com/ (referenced in vector-DB comparisons) | Easiest local-first vector store for prototyping | Free, open source |
| FAISS | https://github.com/facebookresearch/faiss | Fastest in-process similarity search library (no built-in persistence/metadata) | Free |
| Qdrant | https://qdrant.tech/ | Production-grade vector DB with filtering & persistence | Free self-host, paid cloud |
| Weaviate | https://weaviate.io/ | Hybrid vector + keyword search | Free self-host, paid cloud |
| Pinecone | https://www.pinecone.io/ | Fully managed vector DB, zero-ops | Paid (usage-based, free tier available) |

### Browser-automation-for-agents tooling
| Tool | Link | Notes | Free/Paid |
|---|---|---|---|
| Playwright (+ MCP server) | https://github.com/microsoft/playwright | Foundational cross-browser automation, MCP server for structured agent control | Free |
| browser-use | https://github.com/browser-use/browser-use | LLM-driven browser agent library | Free |
| Skyvern | https://github.com/skyvern-ai/skyvern | Vision+LLM browser automation, robust to unseen sites | Free core (AGPL-3.0), paid cloud |
| agent-browser (Vercel Labs) | https://github.com/vercel-labs/agent-browser | CLI browser driver purpose-built for agent snapshotting/recording | Free |

### Observability / evaluation tooling
| Tool | Link | Notes | Free/Paid |
|---|---|---|---|
| LangSmith | https://www.langchain.com/langsmith/observability | Tracing, debugging, evaluation, monitoring for agents (framework-agnostic) | Free tier, paid plans |
| Langfuse | https://langfuse.com/ | Open-source LLM/agent observability and evaluation platform | Free self-host/open source, paid cloud |
| AgentOps | https://www.agentops.ai/ | Agent run tracking/session replay/cost monitoring | Free tier, paid plans |

### Protocols
| Protocol | Link | Notes | Free/Paid |
|---|---|---|---|
| Model Context Protocol (MCP) | https://www.anthropic.com/news/model-context-protocol | Standard for connecting agents to tools/data | Free, open standard |
| Agent2Agent Protocol (A2A) | https://www.deeplearning.ai/courses/a2a-the-agent2agent-protocol | Standard for agent-to-agent interoperability | Free, open standard |

---

## 8. Forums / Communities

- **r/AI_Agents (Reddit)** — https://www.reddit.com/r/AI_Agents/ — Largest general subreddit for agent projects, orchestration, memory, tool use, and real deployments; free.
- **r/LangChain (Reddit)** — https://www.reddit.com/r/LangChain/ — Framework-specific discussion, comparisons (e.g., LangGraph vs CrewAI vs AutoGen threads); free.
- **r/LocalLLaMA (Reddit)** — referenced via Hugging Face course discussion thread https://www.reddit.com/r/LocalLLaMA/comments/1i1zcnq/hugging_face_is_doing_a_free_and_certified_course/ — Active community for local-model agent builders; free.
- **r/AgentsOfAI (Reddit)** — https://www.reddit.com/r/AgentsOfAI/ — Agent-tutorial-heavy subreddit with practitioner walkthroughs; free.
- **AutoGen Discord / GitHub Discussions** — linked from https://github.com/microsoft/autogen — Official support community for AutoGen/Agent Framework; free.
- **CrewAI Community Forum** — https://community.crewai.com/ — Official CrewAI discussion forum; free.
- **Hugging Face Discuss — Agents Course category** — https://discuss.huggingface.co/ (see thread https://discuss.huggingface.co/t/new-framework-smolagents/135421) — Official Q&A space tied to the free Agents Course; free.
- **LangChain Community / Academy discussions** — https://academy.langchain.com/ — Official learning community tied to LangChain Academy courses; free.

---

## 9. YouTube Channels / Podcasts Dedicated to AI Agents

### YouTube
- **freeCodeCamp.org** — https://www.youtube.com/@freecodecamp — Full-length free courses on agents, LangGraph, and autonomous agent building (see §2/§3); free.
- **AI Engineer (@aiDotEngineer)** — https://www.youtube.com/@aiDotEngineer — Official channel of the AI Engineer conference series; heavy agent-engineering track content (Summit 2025 "Agent Engineering Day," talks on evaluating agents, agent dev lifecycle); free.
- **DeepLearning.AI** — https://learn.deeplearning.ai/index — Hosts video content for all its short courses, many agent-specific (see §2); free.
- **Microsoft Developer / Agent Framework devblogs channel** — https://learn.microsoft.com/en-us/shows/ai-agents-for-beginners/ — Companion video series for the "AI Agents for Beginners" course; free.

### Podcasts
- **Latent Space: The AI Engineer Podcast** — https://www.latent.space/podcast (about/agents tag: https://www.latent.space/p/agent) — Deep technical interviews on agent engineering, agent infra, and agent labs; treats agents as a first-class recurring topic; free.
- **Jotform AI Agents Podcast** — https://www.jotform.com/podcast/ai-agents/ — Dedicated podcast on AI agents with practical examples (support bots, research agents); free.
- **"AI Trends 2025: AI Agents and Multi-Agent Systems" (with Victor Dibia)** — https://podcasts.apple.com/us/podcast/ai-trends-2025-ai-agents-and-multi-agent-systems/id1116303051?i=1000690895080 — Episode-length deep dive on what differentiates agents from traditional software; free.
- **"The State of AI Agents in 2025 & How to Use Them"** — https://podcasts.apple.com/us/podcast/the-state-of-ai-agents-in-2025-how-to-use-them/id1738550343?i=1000727002634 — Covers hype vs. reality, MCP, A2A; free.

---

## 10. Evaluation and Safety Resources

How to evaluate agent reliability, common failure modes, guardrail/sandboxing practices.

### Evaluation frameworks & benchmarks
- **Anthropic — "Demystifying Evals for AI Agents"** — https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents — Official Anthropic guidance on building agent eval suites; free.
- **Galileo — "Agent Evaluation Framework: Metrics, Rubrics, Benchmarks"** — https://galileo.ai/blog/agent-evaluation-framework-metrics-rubrics-benchmarks — Practical breakdown of outcome vs. trajectory vs. reliability vs. safety metrics; free.
- **LangChain — "How We Benchmark Deep Agents"** — https://www.langchain.com/blog/how-we-benchmark-deep-agents — First-party methodology for benchmarking long-horizon agents; free.
- **GAIA benchmark** — https://huggingface.co/spaces/gaia-benchmark/leaderboard (paper: https://ai.meta.com/research/publications/gaia-a-benchmark-for-general-ai-assistants/) — General-assistant benchmark testing reasoning, tool use, web browsing, multimodality, with a live public leaderboard; free.
- **THUDM/AgentBench** — https://github.com/THUDM/AgentBench — Cross-domain benchmark for agent decision-making across many environments; free.
- **WebArena** — referenced in agent-eval roundups (e.g., https://galileo.ai/blog/agent-evaluation-framework-metrics-rubrics-benchmarks) — Realistic web-navigation benchmark for browser agents; free.
- **tau-bench / tau2-bench** — referenced in https://sierra.ai/blog/benchmarking-ai-agents — Customer-service, policy-constrained tool-use benchmarks emphasizing reliability across repeated runs; free.
- **SWE-bench Verified** — referenced via agent-benchmark roundups — Real GitHub-issue-patching benchmark for coding agents; free.
- **philschmid/ai-agent-benchmark-compendium** — https://github.com/philschmid/ai-agent-benchmark-compendium — One-stop curated compendium of agent benchmarks; free.
- **Evidently AI — "AI Agent Benchmarks"** — https://www.evidentlyai.com/blog/ai-agent-benchmarks — Survey/comparison of the major public agent benchmarks; free.

### Safety / guardrails / sandboxing
- **OpenAI — "A Practical Guide to Building Agents" (guardrails chapter)** — https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/ — Input filtering, tool-use checks, human-in-the-loop escalation; free.
- **Anthropic — "Building Effective Agents"** (safety framing) — https://www.anthropic.com/engineering/building-effective-agents — Discusses transparency and staged rollout of agent autonomy; free.
- **Simon Willison — "The Lethal Trifecta for AI Agents"** — https://simonw.substack.com/p/the-lethal-trifecta-for-ai-agents — The single most-cited mental model for prompt-injection/exfiltration risk in agents; free.
- **Arthur AI — "Best Practices for Building Agents: Guardrails"** — https://www.arthur.ai/blog/best-practices-for-building-agents-guardrails — Layered guardrail architecture (deterministic pre-checks + selective LLM-judge post-checks); free.
- **Hatchworks — "AI Agent Guardrails"** — https://hatchworks.com/blog/ai-agents/ai-agent-guardrails/ — Practical checklist: least privilege, tool allowlists, human approval gates, logging; free.
- **Snyk — "The Future of AI Agent Security & Guardrails"** — https://snyk.io/blog/future-of-ai-agent-security-guardrails/ — Security-engineering perspective on sandboxing untrusted agent execution; free.
- **OSFoundry — "Autonomous Agent Guardrails"** — https://osfoundry.io/articles/autonomous-agent-guardrails — Sandboxing/isolation patterns (containers, ephemeral VMs, scoped credentials); free.
- **BigID — "Agentic AI Guardrails"** — https://bigid.com/blog/agentic-ai-guardrails/ — Enterprise governance/data-security angle on agent guardrails; free.

---

## 11. Practice Project Ideas

Concrete, progressively harder build targets, aligned with the resources above.

1. **From-scratch ReAct loop (no framework).** Implement Thought→Action→Observation in ~100 lines of Python using only an LLM API and 1-2 tools (calculator, a search function). Study `ysymyth/ReAct` and `yoheinakajima/babyagi` as references.
2. **Web research agent.** Give the agent a search tool + a fetch/read-page tool; have it research a question and produce a cited summary. Good frameworks to try: OpenAI Agents SDK, LangGraph, or smolagents `CodeAgent`.
3. **Multi-tool personal-assistant agent.** Combine calendar/notes/file/search tools with memory (Mem0 or a simple vector store) so the assistant remembers preferences across sessions. Use the DeepLearning.AI "Agent Memory" course as a guide.
4. **Browser-automation agent.** Use `browser-use` or Playwright's MCP server to have an agent complete a real multi-step web task (e.g., "find the cheapest flight and fill out the booking form up to payment").
5. **Small multi-agent debate/collaboration demo.** Implement the "Multiagent Debate" pattern (arxiv 2305.14325-style loop) with 2-3 agent instances arguing toward a shared answer, and compare with a single-agent baseline.
6. **Reflexion-style self-improving agent.** Add a self-critique/reflection step after task failure, store the reflection in memory, and retry — measure improvement over N attempts on a small coding or puzzle benchmark.
7. **Agent evaluation harness.** Build a tiny eval suite (5-10 tasks + rubric) for one of the agents above, scoring both outcome success and trajectory efficiency, inspired by `philschmid/ai-agent-benchmark-compendium`.
8. **Guardrailed agent.** Add input sanitization, a tool allowlist, and a human-approval gate for "risky" tool calls (e.g., sending an email or making a purchase) to any of the above agents, and write a short adversarial test (prompt injection) against it.

---

## 12. Cheat Sheets / Quick-Reference Roadmaps / Glossaries

- **Digital Applied — "AI Agent Glossary: 60 Essential Terms"** — https://www.digitalapplied.com/blog/ai-agent-glossary-2026-60-essential-terms — Comprehensive term-by-term glossary (agent, agentic loop, orchestration, MCP, A2A, guardrails, etc.); free.
- **BetterClaw — "AI Agent Glossary"** — https://www.betterclaw.io/blog/ai-agent-glossary — Alternative glossary with slightly different term coverage, useful cross-reference; free.
- **Maven AGI — "Agentic AI Glossary: 100 Essential AI Agent Terms for Enterprise Buyers"** — https://www.mavenagi.com/resources/agentic-ai-glossary-100-essential-ai-agent-terms-for-enterprise-buyers — Enterprise-focused glossary, good for translating technical terms to business language; free.
- **Wikipedia — Glossary of Artificial Intelligence** — https://en.wikipedia.org/wiki/Glossary_of_artificial_intelligence — General AI/ML glossary, useful backstop for terms not agent-specific; free.
- **Avi Chawla — "30 Agentic AI Terms AI Engineers Should Know" (LinkedIn)** — https://www.linkedin.com/posts/avi-chawla_30-agentic-ai-terms-ai-engineers-should-know-activity-7393956947571617792-t9XR — Compact practitioner cheat-sheet; free.
- **Andrew Ng's Four Agentic Design Patterns (one-page mental model)** — https://learn.deeplearning.ai/courses/agentic-ai/lesson/rm9bg7/agentic-design-patterns — The best single quick-reference for choosing which agentic pattern to reach for; free.

---

## 13. Suggested Learning Progression

**Beginner (concepts + first agent, ~1-2 weeks)**
1. Read Anthropic's "Building Effective Agents" and OpenAI's "Practical Guide to Building Agents" (§1) — get the vocabulary and mental models straight.
2. Read the ReAct paper (or its Google Research summary) and skim Andrew Ng's four agentic design patterns (§1, §12).
3. Do the Hugging Face Agents Course, Units 1-2 (§2) — it's free, structured, and covers smolagents + LlamaIndex agents hands-on.
4. Build Practice Project #1 (from-scratch ReAct loop) and #2 (web research agent) from §11.

**Intermediate (frameworks, memory, RAG, ~3-5 weeks)**
5. Take DeepLearning.AI's "AI Agents in LangGraph" and "Multi AI Agent Systems with crewAI" (§2) to learn a production framework properly.
6. Study RAG fundamentals and build a small RAG pipeline in both LangChain and LlamaIndex (§1/§7 links).
7. Read the Redis/Atlan memory-architecture posts and DeepLearning.AI's "Agent Memory" course (§4/§2); wire up Mem0 or a vector store (Chroma/Qdrant) into your assistant agent.
8. Build Practice Projects #3 (multi-tool assistant with memory) and #4 (browser-automation agent) from §11.
9. Read the Toolformer and Reflexion papers (§4); implement Practice Project #6 (self-improving agent).

**Advanced (multi-agent, evaluation, safety, ~ongoing)**
10. Read the multi-agent debate paper and a recent multi-agent survey (§4); build Practice Project #5 (debate demo).
11. Take Berkeley's CS294 "Large Language Model Agents" lecture series (§2) for research-level depth on planning, RAG, safety, and multimodal agents.
12. Set up LangSmith or Langfuse tracing on one of your agents (§7); build Practice Project #7 (evaluation harness) using GAIA/AgentBench/tau-bench as inspiration (§10).
13. Read the safety/guardrails resources (§10) and implement Practice Project #8 (guardrailed agent + adversarial test).
14. Explore the broader framework ecosystem (AutoGen/Agent Framework, Semantic Kernel, Skyvern) and MCP/A2A protocols (§7) to understand interoperability trends; consider one paid specialization (§2) if you want a certificate or a more guided capstone.
15. Stay current via Latent Space podcast, the AI Engineer YouTube channel, and r/AI_Agents (§8/§9).
