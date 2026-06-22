# Awesome AI Agent Benchmarks

A curated, dimension-organized index of **100 benchmarks** for evaluating LLM-based AI agents — coding, web, computer use, tool use, reasoning, multi-agent, science, safety, and real-world work.

Evaluating AI agents is hard: a single accuracy number rarely captures whether a system can fix a real GitHub issue, drive a live browser, recover from a prompt injection, or plan a trip under constraints. This list organizes the benchmarks that matter across **9 capability dimensions** — from the headline evals reported in every frontier model card (SWE-bench Verified, τ-bench, GAIA, OSWorld) to the frontier stress-tests where even the best agents score in the single digits. Each entry says what it actually tests, with links to the paper, code, and live leaderboard.

> Curated by the [first-tree](https://github.com/unispark-inc/first-tree?ref=awesome-ai-agent-benchmarks) team.

---

## Contents

- [Coding & Software Engineering](#coding--software-engineering) (11)
- [Web Browsing & Navigation](#web-browsing--navigation) (12)
- [Computer Use (GUI / OS)](#computer-use-gui--os) (11)
- [Tool Use & Function Calling](#tool-use--function-calling) (10)
- [Reasoning & Planning](#reasoning--planning) (10)
- [Multi-Agent](#multi-agent) (11)
- [Science & Research](#science--research) (12)
- [Safety, Security & Robustness](#safety-security--robustness) (12)
- [General & Real-World Work](#general--real-world-work) (11)

---

## At a glance

One flagship benchmark per dimension. See each section for the full set.

| Benchmark | Dimension | What it tests | Tasks |
|---|---|---|---|
| [SWE-bench](https://github.com/SWE-bench/SWE-bench) | Coding | Given a real GitHub issue and the full repository, the agent must prod… | 2294 |
| [WebArena](https://github.com/web-arena-x/webarena) | Web Browsing | Complete high-level natural-language tasks (e-commerce, forums, GitLab… | 812 |
| [OSWorld](https://github.com/xlang-ai/OSWorld) | Computer Use | Execute 369 open-ended real-computer tasks (file ops, desktop apps, we… | 369 |
| [BFCL (Berkeley Function-Calling Leaderboard)](https://github.com/ShishirPatil/gorilla) | Tool Use | Given a natural-language request and a set of function/API schemas, th… | thousands (V1-V4, ~3700+ across categories) |
| [GAIA](https://huggingface.co/datasets/gaia-benchmark/GAIA) | Reasoning | Answer 466 real-world questions that each require a chained sequence o… | 466 questions (300 held out for the leaderboard, 3 difficulty levels) |
| [SOTOPIA](https://github.com/sotopia-lab/sotopia) | Multi-Agent | Two LLM agents role-play assigned characters with private, sometimes-c… | 90 social scenarios |
| [ScienceAgentBench](https://github.com/OSU-NLP-Group/ScienceAgentBench) | Science | Given a real scientific data-analysis task, the agent must write a sel… | 102 |
| [AgentHarm](https://github.com/UKGovernmentBEIS/inspect_evals) | Safety, Security | Given an explicitly malicious multi-step request (e.g. fraud, cybercri… | 110 base behaviors (440 with augmentations) across 11 harm categories, 104 tools |
| [GAIA](https://github.com/aymeric-roucher/GAIA) | General | Answer 466 human-authored real-world assistant questions that require … | 466 |

---

## Coding & Software Engineering

*Resolving real issues, writing code, building libraries, working in the terminal.*

### SWE-bench
Given a real GitHub issue and the full repository, the agent must produce a code patch (diff) that resolves the issue and passes the repo's hidden test suite. · **2294 tasks**

> The foundational real-world software-engineering benchmark (ICLR 2024, Princeton). 2,294 tasks across 12 Python repos. Cited everywhere and the basis for most agentic coding evals and model cards.

[paper](https://arxiv.org/abs/2310.06770) · [code](https://github.com/SWE-bench/SWE-bench) · [leaderboard](https://www.swebench.com/)

### SWE-bench Verified
Same task as SWE-bench (resolve a real GitHub issue via a patch that passes hidden tests), but on a 500-instance human-validated subset where problems are confirmed solvable and tests are correct. · **500 tasks**

> The de facto industry-standard coding-agent metric, built with OpenAI human annotators. Headline number in nearly every frontier-model release (Claude, GPT, Gemini) and the most-watched coding leaderboard.

[paper](https://arxiv.org/abs/2310.06770) · [code](https://github.com/SWE-bench/SWE-bench) · [leaderboard](https://www.swebench.com/verified.html)

### SWE-bench Multimodal
Resolve real GitHub issues in user-facing JavaScript repos where the problem statement or tests include images (UI bugs, data-viz, mapping), requiring visual reasoning plus code editing. · **619 tasks**

> First benchmark testing coding agents on visual/front-end software domains; 619 tasks from 17 JS repos. Top systems resolve only ~12%, exposing a large gap beyond text-only Python tasks.

[paper](https://arxiv.org/abs/2410.03859) · [code](https://github.com/SWE-bench/SWE-bench)

### Multi-SWE-bench
Resolve real GitHub issues via patches that pass hidden tests, but across 7 non-Python languages (Java, TypeScript, JavaScript, Go, Rust, C, C++). · **1632 tasks**

> First large multilingual issue-resolving benchmark (ByteDance Seed), 1,632 issues. Increasingly used to show coding agents generalize beyond Python.

[paper](https://arxiv.org/abs/2504.02605) · [code](https://github.com/multi-swe-bench/multi-swe-bench)

### LiveCodeBench
Solve competitive-programming problems continuously scraped from LeetCode, AtCoder and Codeforces, with code generation plus self-repair, code execution, and test-output prediction. · **1000+ tasks**

> The standard contamination-free code-generation benchmark; problems are date-stamped so models are scored only on problems released after their training cutoff. Widely cited and used in model cards.

[paper](https://arxiv.org/abs/2403.07974) · [code](https://github.com/LiveCodeBench/LiveCodeBench)

### BigCodeBench
Write Python functions that correctly compose multiple library/API calls (139 libraries, 7 domains) to satisfy complex natural-language instructions, verified by rich test cases. · **1140 tasks**

> ICLR 2025; the leading benchmark for realistic library-heavy coding (1,140 tasks, 723 function calls). Best LLMs reach ~60% vs 97% human, making it a hard, widely-used signal beyond toy code generation.

[paper](https://arxiv.org/abs/2406.15877) · [code](https://github.com/bigcode-project/bigcodebench) · [leaderboard](https://bigcode-bench.github.io/)

### Aider Polyglot
Complete 225 hard Exercism exercises across C++, Go, Java, JavaScript, Python and Rust, applying edits in a specified diff format with one retry shown unit-test feedback. · **225 tasks**

> Highly influential practitioner benchmark from the Aider project; measures both correctness and whether models can edit code in the right format. Frequently cited in frontier-model launches.

[code](https://github.com/Aider-AI/aider) · [leaderboard](https://aider.chat/docs/leaderboards/)

### RepoBench
Repository-level code auto-completion: retrieve relevant cross-file context, predict the next line of code given in-file and cross-file context, and combine both in an end-to-end pipeline.

> ICLR 2024; one of the most-cited repo-level (multi-file) completion benchmarks for Python and Java, widely used to evaluate code models' cross-file context handling.

[paper](https://arxiv.org/abs/2306.03091) · [code](https://github.com/Leolty/repobench)

### Commit0
Build an entire Python library from scratch given only an API specification document and a suite of interactive unit tests, iterating with static-analysis and execution feedback. · **54 tasks**

> Pushes agents beyond one-shot generation to long-horizon, spec-driven library implementation across 54 libraries; no agent yet reproduces full libraries, making it a hard frontier benchmark.

[paper](https://arxiv.org/abs/2412.01769) · [code](https://github.com/commit-0/commit0) · [leaderboard](https://commit-0.github.io/)

### SWE-Lancer
Complete real paid Upwork freelance software-engineering tasks (bug fixes to feature builds) graded by end-to-end tests, plus managerial tasks choosing between implementation proposals. · **1488 tasks**

> OpenAI benchmark of 1,400+ tasks worth $1M in real payouts; maps model performance to dollar value. The leading economically-grounded real-world SWE benchmark, used in OpenAI model evaluations.

[paper](https://arxiv.org/abs/2502.12115) · [code](https://github.com/openai/SWELancer-Benchmark)

### Terminal-Bench
Autonomously complete hard, end-to-end tasks in a real command-line environment (compiling code, training models, configuring servers, sysadmin, security) verified by automated checks. · **89 tasks**

> Stanford / Laude Institute benchmark for terminal/CLI agents; widely adopted across scaffolds (Codex CLI, OpenHands, Aider, Claude Code). v2.0 evaluates 89 tasks with multiple trials and 100+ agents on the leaderboard.

[code](https://github.com/laude-institute/terminal-bench) · [leaderboard](https://www.tbench.ai/leaderboard)

---

## Web Browsing & Navigation

*Driving live or cloned websites: shopping, research, form-filling, multi-step navigation.*

### WebArena
Complete high-level natural-language tasks (e-commerce, forums, GitLab, CMS) end-to-end in self-hosted, fully-functional clones of real websites, scored by execution-based functional correctness. · **812 tasks**

> The canonical reproducible web-agent benchmark (ICLR 2024); GPT-4 baseline ~14% vs human ~78%. Widely cited and used in frontier-model agent evals; ServiceNow released WebArena-Verified (2025) as an audited version.

[paper](https://arxiv.org/abs/2307.13854) · [code](https://github.com/web-arena-x/webarena) · [leaderboard](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ)

### VisualWebArena
Solve realistic visually-grounded web tasks (image-text inputs, spatial reasoning) on self-hosted Classifieds, Shopping, and Reddit sites, evaluated by execution-based correctness. · **910 tasks**

> ACL 2024 multimodal extension of WebArena; the standard test for vision-grounded web agents. Top agents reached ~16% vs human ~89%, exposing a large multimodal gap.

[paper](https://arxiv.org/abs/2401.13649) · [code](https://github.com/web-arena-x/visualwebarena) · [leaderboard](https://jykoh.com/vwa)

### WebVoyager
Complete end-to-end tasks on 15 live, high-traffic real websites (Amazon, Booking, Google Maps, GitHub, etc.) using screenshots + accessibility tree, scored by a GPT-4V automatic judge. · **643 tasks**

> ACL 2024; one of the most-cited 'agent on the live web' benchmarks and a de-facto standard for multimodal browsing agents. Its GPT-4V auto-eval (~85% agreement with humans) is widely reused.

[paper](https://arxiv.org/abs/2401.13919) · [code](https://github.com/MinorJerry/WebVoyager)

### Mind2Web
Predict the correct action sequence (element selection + operation) to complete open-ended tasks across 137 real websites from offline interaction traces, testing cross-domain/website generalization. · **2350 tasks**

> NeurIPS 2023 Spotlight; the first benchmark for generalist web agents and a foundational dataset spanning 31 domains / 137 sites. Heavily used for training and offline action-prediction evaluation.

[paper](https://arxiv.org/abs/2306.06070) · [code](https://github.com/OSU-NLP-Group/Mind2Web) · [leaderboard](https://osu-nlp-group.github.io/Mind2Web/)

### Online-Mind2Web
Execute 300 realistic tasks on 136 live websites in an online setting, judged by the WebJudge LLM-as-a-judge protocol, to measure true end-to-end success rather than offline action matching. · **300 tasks**

> COLM 2025 ('An Illusion of Progress?'); a current, widely-cited live-web benchmark used by browser-use and frontier labs. Showed prior results were over-optimistic (OpenAI Operator ~61%). WebJudge auto-eval ~85% human agreement.

[paper](https://arxiv.org/abs/2504.01382) · [code](https://github.com/OSU-NLP-Group/Online-Mind2Web) · [leaderboard](https://huggingface.co/datasets/osunlp/Online-Mind2Web)

### WebShop
Navigate a simulated e-commerce site of 1.18M real products to find, customize, and purchase the item matching a natural-language shopping instruction, scored by attribute/price matching. · **12087 tasks**

> NeurIPS 2022; the foundational grounded-language web-interaction benchmark (Princeton NLP, ReAct team). Still a standard sim-to-real shopping testbed; best model 29% vs human 59%.

[paper](https://arxiv.org/abs/2207.01206) · [code](https://github.com/princeton-nlp/WebShop)

### GAIA
Answer real-world assistant questions that require multi-step reasoning, tool use, and web browsing to find and synthesize information, with short verifiable answers. · **466 tasks**

> Meta/HuggingFace/AutoGPT benchmark; the most prominent general-assistant eval where web browsing is core. Humans ~92% vs GPT-4+plugins ~15%. Heavily used in agent framework papers and model cards; its web subset is reused in WebVoyager.

[paper](https://arxiv.org/abs/2311.12983) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### BrowserGym
A unified gym-like environment with a standard observation/action space that lets a single web agent be evaluated across many browsing benchmarks (WebArena, VisualWebArena, WorkArena, MiniWoB, WebLINX, AssistantBench).

> ServiceNow's standardization layer (paired with AgentLab) that has become the common harness for running and comparing web agents across benchmarks; widely adopted in academic and industry web-agent research.

[paper](https://arxiv.org/abs/2412.05467) · [code](https://github.com/ServiceNow/BrowserGym)

### WorkArena / WorkArena++
Perform common enterprise knowledge-work tasks on the live ServiceNow platform (filtering lists, filling forms, service catalog, dashboards, menu navigation), plus compositional multi-step tasks in WorkArena++. · **33 tasks / 19,912 instances (WorkArena L1); 682 (WorkArena++) tasks**

> ICML 2024 (L1) and NeurIPS 2024 (WorkArena++); the leading enterprise/UI web-agent benchmark, integrated into BrowserGym. Best agents only ~55%, highlighting enterprise-software difficulty.

[paper](https://arxiv.org/abs/2403.07718) · [code](https://github.com/ServiceNow/WorkArena) · [leaderboard](https://servicenow.github.io/WorkArena/)

### AssistantBench
Solve realistic, time-consuming open-web tasks (e.g. 'which nearby gyms have weekend classes before 7AM?') that require browsing many pages across hundreds of real sites and returning a precise answer. · **214 tasks**

> EMNLP 2024; a hard open-web information-seeking benchmark (525+ pages across 258 sites) where no system exceeds ~26 points. Integrated into BrowserGym and used to probe long-horizon browsing.

[paper](https://arxiv.org/abs/2407.15711) · [code](https://github.com/oriyor/assistantbench) · [leaderboard](https://huggingface.co/spaces/AssistantBench/leaderboard)

### BrowseComp
Answer 'inverted' questions that require persistent, creative web browsing to locate hard-to-find, entangled facts, with short answers that are easy to verify against references. · **1266 tasks**

> OpenAI (2025); the reference benchmark for deep-research / persistent-browsing agents, used in OpenAI Deep Research and frontier-model model cards. Designed so answers take humans 10+ minutes and aren't on page one of Google.

[paper](https://arxiv.org/abs/2504.12516) · [code](https://github.com/openai/simple-evals) · [leaderboard](https://llm-stats.com/benchmarks/browsecomp)

### MiniWoB++ (MiniWoB)
Complete 100+ small synthetic web UI interaction tasks (click buttons, fill fields, use date pickers, drag-and-drop) in controlled mini web pages, scored by task completion reward. · **100+ tasks**

> The classic foundational web-UI control benchmark (originally World of Bits, 2017); still a standard low-level interaction testbed integrated into BrowserGym and used to pretrain/evaluate GUI grounding.

[paper](https://arxiv.org/abs/1802.08802) · [code](https://github.com/Farama-Foundation/miniwob-plusplus)

---

## Computer Use (GUI / OS)

*Operating real desktops, mobile, and GUI apps via screenshots and clicks.*

### OSWorld
Execute 369 open-ended real-computer tasks (file ops, desktop apps, web, multi-app workflows) in a live Ubuntu/Windows VM, scored by execution-based checks on final system state. · **369 tasks**

> The de facto standard for desktop computer-use agents. Used in model cards/blogs by Anthropic, OpenAI, and others; OSWorld-Verified is the canonical leaderboard. Human ~72% vs early agents ~12%, now ~60%+.

[paper](https://arxiv.org/abs/2404.07972) · [code](https://github.com/xlang-ai/OSWorld) · [leaderboard](https://os-world.github.io/)

### WindowsAgentArena (WAA)
Complete 154 multi-step Windows-OS tasks across real apps (Office, VS Code, Edge, File Explorer, Settings, Paint) in parallelizable Docker/Azure VMs with execution-based evaluation. · **154 tasks**

> Microsoft's Windows analogue to OSWorld; built on the OSWorld framework. Heavily used for benchmarking enterprise/desktop agents; full eval runs in ~20 min via Azure parallelization.

[paper](https://arxiv.org/abs/2409.08264) · [code](https://github.com/microsoft/WindowsAgentArena)

### AndroidWorld
Complete 116 programmatic tasks across 20 real Android apps on a live emulator, with dynamically randomized parameters yielding millions of task variations and reward signals. · **116 tasks**

> Google Research's reference benchmark for mobile/GUI agents; widely cited and used in mobile-agent model evals. Human ~80% vs early M3A agent ~30.6%.

[paper](https://arxiv.org/abs/2405.14573) · [code](https://github.com/google-research/android_world) · [leaderboard](https://google-research.github.io/android_world/)

### ScreenSpot (SeeClick)
Given a natural-language instruction and a screenshot, output the pixel coordinates of the correct UI element across mobile, desktop, and web (1,200+ instructions). · **1272 tasks**

> The original realistic GUI-grounding benchmark; foundational reference for measuring click-localization accuracy, cited across nearly all GUI-agent papers and grounding model cards.

[paper](https://arxiv.org/abs/2401.10935) · [code](https://github.com/njucckevin/SeeClick)

### ScreenSpot-Pro
Locate tiny, cluttered UI targets from instructions on ultra-high-resolution professional desktop software (CAD, IDEs, office, scientific) via 1,581 expert-annotated screenshot-instruction pairs. · **1581 tasks**

> The hard, high-resolution successor to ScreenSpot; targets average 0.07% of screen area. Standard stress-test for grounding models (best model ~18.9% at release).

[paper](https://arxiv.org/abs/2504.07981) · [code](https://github.com/likaixin2000/ScreenSpot-Pro-GUI-Grounding) · [leaderboard](https://gui-agent.github.io/grounding-leaderboard/)

### GUI-World
Answer GUI-understanding questions over 12,000+ annotated GUI videos spanning desktop, mobile, web, software, and XR, covering static, dynamic, and sequential GUI content. · **12000 tasks**

> ICLR 2025; first video-based GUI understanding benchmark/dataset. Used to evaluate and instruction-tune GUI-oriented multimodal LLMs (GUI-Vid).

[paper](https://arxiv.org/abs/2406.10819) · [code](https://github.com/Dongping-Chen/GUI-World) · [leaderboard](https://gui-world.github.io/)

### AgentStudio
Run general virtual-agent tasks in a live environment with video observations and GUI+API actions (205 tasks over terminal, Gmail, VS Code, etc.), plus grounding/video-learning/success-detection sub-benchmarks. · **205 tasks**

> ICLR 2025; a trinity of environment + tools + benchmarks (GroundUI, IDMBench, CriticBench) for building general computer agents. Used for cross-cutting GUI-agent capability evaluation.

[paper](https://arxiv.org/abs/2403.17918) · [code](https://github.com/ltzheng/agent-studio) · [leaderboard](https://ltzheng.github.io/agent-studio/)

### WebArena
Complete 812 long-horizon web tasks (shopping, GitLab, Reddit-style forum, CMS, maps) in fully functional self-hosted web apps, scored by functional correctness of the end state. · **812 tasks**

> The dominant reproducible web-agent benchmark; dozens of agents compete on its leaderboard. Human ~78% vs original GPT-4 agent ~14%, now 70%+.

[paper](https://arxiv.org/abs/2307.13854) · [code](https://github.com/web-arena-x/webarena) · [leaderboard](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ)

### WebVoyager
Drive a real browser end-to-end against 15 live production websites (Amazon, Google Flights, BBC, etc.) to complete 643 real-world tasks, auto-evaluated by a GPT-4V judge over the screenshot trajectory. · **643 tasks**

> Widely-used live-web multimodal agent benchmark; popularized the screenshot-based browsing agent and the VLM-as-judge evaluation protocol (85% agreement with humans).

[paper](https://arxiv.org/abs/2401.13919) · [code](https://github.com/MinorJerry/WebVoyager)

### Mind2Web
Predict the correct action sequence (element selection + operation) to complete 2,000+ crowd-sourced open-ended tasks across 137 real websites spanning 31 domains. · **2350 tasks**

> NeurIPS 2023 Spotlight; the first generalist-web-agent benchmark and a foundational dataset for training/evaluating web action-prediction models, very heavily cited.

[paper](https://arxiv.org/abs/2306.06070) · [code](https://github.com/OSU-NLP-Group/Mind2Web)

### SPA-Bench
Evaluate smartphone agents on 340 single-app and cross-app tasks across English and Chinese system/third-party Android apps via a plug-and-play live-device framework with automated multi-metric scoring. · **340 tasks**

> Comprehensive smartphone-agent benchmark integrating 10+ agents in one framework; widely used for cross-app and bilingual mobile-agent evaluation including resource-consumption metrics.

[paper](https://arxiv.org/abs/2410.15164) · [code](https://github.com/ai-agents-2030/SPA-Bench)

---

## Tool Use & Function Calling

*Calling APIs and tools correctly, multi-turn, with the right arguments.*

### BFCL (Berkeley Function-Calling Leaderboard)
Given a natural-language request and a set of function/API schemas, the agent must emit syntactically correct function calls (single, parallel, multiple, multi-turn, and agentic) that an AST/state checker validates for correctness. · **thousands (V1-V4, ~3700+ across categories) tasks**

> The de-facto industry standard for function-calling evaluation; cited in nearly every model card (OpenAI, Anthropic, Google, Mistral, etc.). V3 added multi-turn/multi-step and V4 (2025) added real-world agentic tasks with web search, memory, and format-sensitivity.

[paper](https://proceedings.mlr.press/v267/patil25a.html) · [code](https://github.com/ShishirPatil/gorilla) · [leaderboard](https://gorilla.cs.berkeley.edu/leaderboard.html)

### tau-bench (τ-bench)
The agent plays a customer-service rep that must converse with an LLM-simulated user while calling domain APIs (retail, airline) under written policy constraints, judged by the final database state plus a pass^k consistency metric. · **165 (115 retail + 50 airline) tasks**

> From Sierra (Bret Taylor); the most influential tool-agent-user interaction benchmark. Heavily used in frontier model cards (Anthropic, OpenAI) as the canonical agentic tool-use eval; pass^k exposes reliability gaps.

[paper](https://arxiv.org/abs/2406.12045) · [code](https://github.com/sierra-research/tau-bench) · [leaderboard](https://www.taubench.com/)

### tau2-bench (τ²-bench)
Extends tau-bench to dual-control settings where both the agent AND the simulated user can call tools (modeled as a Dec-POMDP), with a Telecom troubleshooting domain plus retail and airline and a compositional task generator. · **hundreds across telecom/retail/airline tasks**

> The 2025 successor to tau-bench; now the headline conversational tool-use eval reported in current frontier model launches. Adds collaborative dual-control troubleshooting that single-agent benchmarks miss.

[paper](https://arxiv.org/abs/2506.07982) · [code](https://github.com/sierra-research/tau2-bench) · [leaderboard](https://www.taubench.com/)

### ToolBench (ToolLLM)
Given user instructions, the agent must select and chain calls across 16,000+ real RapidAPI REST APIs (single-tool and multi-tool, with DFSDT solution paths), evaluated by pass rate and win rate against a reference. · **16,464 APIs / 3,451 tools; ~126k instruction-solution pairs tasks**

> ICLR'24 spotlight from OpenBMB; the foundational large-scale real-API tool-learning benchmark and the most-cited baseline for massive-toolset agents. Spawned StableToolBench and many follow-ups.

[paper](https://arxiv.org/abs/2307.16789) · [code](https://github.com/OpenBMB/ToolBench)

### StableToolBench
A stabilized re-implementation of ToolBench that replaces flaky live RapidAPIs with a virtual API server (caching + GPT-4 API simulators) and a solvable pass/win-rate evaluator, so tool-use scores are reproducible. · **subset of ToolBench instructions over 16k+ APIs tasks**

> ACL 2024 Findings; the standard way researchers now run ToolBench because real API instability made the original non-reproducible. Widely used as the stable successor for large-scale tool-learning comparisons.

[paper](https://arxiv.org/abs/2403.07714) · [code](https://github.com/THUNLP-MT/StableToolBench) · [leaderboard](https://zhichengg.github.io/stb.github.io/)

### API-Bank
A runnable benchmark where the agent must plan, retrieve, and call from a pool of 73 executable APIs across multi-turn tool-use dialogues, scored on correct API calls and response quality. · **73 APIs, 314 dialogues, 753 API calls (eval set) tasks**

> EMNLP 2023; one of the earliest and most-cited tool-augmented-LLM benchmarks with a runnable evaluation system, frequently used as a baseline for planning/retrieval/calling abilities.

[paper](https://arxiv.org/abs/2304.08244) · [code](https://github.com/AlibabaResearch/DAMO-ConvAI/tree/main/api-bank)

### ToolSandbox
A stateful, conversational benchmark with an on-policy LLM user simulator where tools mutate shared world state and have implicit inter-tool dependencies, scored via milestone/minefield checks over the trajectory. · **1032 test scenarios tasks**

> From Apple; one of the most-cited benchmarks targeting stateful tool execution and state-dependency/canonicalization challenges that stateless single-turn benchmarks ignore.

[paper](https://arxiv.org/abs/2408.04682) · [code](https://github.com/apple/ToolSandbox)

### ComplexFuncBench
1,000 multi-step, constrained function-calling samples requiring implicit-parameter reasoning, long (>500-token) parameter values, and up to 128k-token long-context, evaluated by the automatic ComplexEval framework. · **1,000 tasks**

> From Zhipu AI (GLM) and Tsinghua; the go-to 2025 benchmark for hard, long-context, multi-step constrained function calling, used in GLM model reporting and reproduced on public leaderboards.

[paper](https://arxiv.org/abs/2501.10132) · [code](https://github.com/zai-org/ComplexFuncBench) · [leaderboard](https://llm-stats.com/benchmarks/complexfuncbench)

### ToolEmu
An LM-emulated sandbox that simulates execution of 311 tools across 36 toolkits from specs alone, paired with an LM safety evaluator that surfaces and scores risky/unsafe agent tool-use failures. · **144 test cases (36 toolkits, 311 tools) tasks**

> ICLR 2024 spotlight; the seminal benchmark for safety/risk of tool-using agents via LM-emulated execution, widely cited as the reference for agent-safety tool-use evaluation.

[paper](https://arxiv.org/abs/2309.15817) · [code](https://github.com/ryoungj/ToolEmu)

### MCP-Universe
The agent connects to 11 real, live Model Context Protocol (MCP) servers across 6 domains (maps, GitHub repo management, finance, 3D design, browser automation, web search) and must discover unknown tools and complete long-horizon real-world tasks with execution-based grading. · **231 tasks**

> From Salesforce AI Research (2025); the first comprehensive benchmark over real running MCP servers, now a key reference for evaluating agents on the live MCP ecosystem (even top models like GPT-5 score under 50%).

[paper](https://arxiv.org/abs/2508.14704) · [code](https://github.com/SalesforceAIResearch/MCP-Universe) · [leaderboard](https://mcp-universe.github.io/)

---

## Reasoning & Planning

*Multi-step problem solving, planning under constraints, hard knowledge.*

### GAIA
Answer 466 real-world questions that each require a chained sequence of reasoning, web browsing, multi-modality handling, and tool use to reach a single unambiguous answer. · **466 questions (300 held out for the leaderboard, 3 difficulty levels) tasks**

> The canonical general-assistant agent benchmark from Meta AI/HuggingFace; humans score ~92% vs ~15% for GPT-4+plugins at release. Widely used in model cards and agent frameworks; also mirrored on the HAL (Princeton) leaderboard.

[paper](https://arxiv.org/abs/2311.12983) · [code](https://huggingface.co/datasets/gaia-benchmark/GAIA) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### AgentBench
Operate as an autonomous agent across 8 distinct interactive environments (OS, database, knowledge graph, card game, lateral-thinking puzzles, web shopping/browsing, household) over multiple turns of reasoning and decision-making. · **8 environments tasks**

> ICLR'24; the first benchmark to systematically evaluate LLM-as-agent across diverse environments. Tested 27+ models and showed poor long-term reasoning/decision-making is the main blocker for usable agents. Heavily cited foundational agent benchmark from Tsinghua (THUDM).

[paper](https://arxiv.org/abs/2308.03688) · [code](https://github.com/THUDM/AgentBench) · [leaderboard](https://docs.google.com/spreadsheets/d/e/2PACX-1vRR3Wl7wsCgHpwUw1_eUXW_fptAPLL3FkhnW_rua0O1Ji_GIVrpTjY5LaKAhwO-WeARjnY_KNw0SYNJ/pubhtml)

### PlanBench
Generate and reason about plans in classical IPC planning domains (Blocksworld, Logistics), including obfuscated variants, to test true planning vs. memorized common-sense retrieval. · **~26,250 prompts across multiple plan-reasoning task types tasks**

> NeurIPS 2023 Datasets & Benchmarks; the standard reference for rigorous, automated-planning-grounded evaluation of LLM planning. Exposed large gaps that persisted even with reasoning models (o1 analysis), making it a touchstone in the LLM-planning literature.

[paper](https://arxiv.org/abs/2206.10498) · [code](https://github.com/karthikv792/LLMs-Planning)

### NATURAL PLAN
Solve natural-language planning problems in Trip Planning, Meeting Planning, and Calendar Scheduling, given tool outputs (Flights/Maps/Calendar) as context, without needing a live tool-use environment. · **3 task families (Trip, Meeting, Calendar planning) tasks**

> From Google DeepMind; isolates pure planning ability and shows sharp degradation as constraints scale (all models <5% at 10 cities in Trip Planning). Frequently used to probe long-horizon constraint-satisfaction planning in frontier models.

[paper](https://arxiv.org/abs/2406.04520) · [code](https://github.com/google-deepmind/natural-plan)

### TravelPlanner
Act as a travel-planning agent that queries a sandbox of ~4M records via tools and produces a complete multi-day itinerary satisfying many hard and soft real-world constraints. · **1,225 planning queries with reference plans tasks**

> ICML'24 Spotlight (OSU NLP); the marquee real-world constrained-planning agent benchmark. GPT-4 reached only 0.6% final-pass rate at release, making it a hard, widely-cited stress test for tool-use + constraint planning.

[paper](https://arxiv.org/abs/2402.01622) · [code](https://github.com/OSU-NLP-Group/TravelPlanner) · [leaderboard](https://huggingface.co/spaces/osunlp/TravelPlannerLeaderboard)

### AgentBoard
Run an LLM agent through 9 multi-turn, partially-observable task families (embodied AI, games, web, tool use) and score fine-grained progress rate rather than only final success. · **9 tasks across 1013 environments tasks**

> NeurIPS 2024 Oral (HKUST NLP). Introduced the influential per-step 'progress rate' metric for analytical agent evaluation, distinguishing it from pass/fail benchmarks; results correlate with reasoning/coding ability.

[paper](https://arxiv.org/abs/2401.13178) · [code](https://github.com/hkust-nlp/AgentBoard) · [leaderboard](https://hkust-nlp.github.io/agentboard/static/leaderboard.html)

### ARC-AGI-2
Infer the hidden transformation rule from a few input-output grid demonstrations and apply it to a novel test grid, requiring abstract compositional reasoning with minimal priors. · **1000 public training + 120 public evaluation tasks tasks**

> François Chollet / ARC Prize Foundation; the most prominent fluid-intelligence / abstract-reasoning benchmark and the basis of the $1M+ ARC Prize. Successor to ARC-AGI-1 (2019); deliberately easy for humans but hard for frontier systems, central to AGI-progress debates.

[paper](https://arxiv.org/abs/2505.11831) · [code](https://github.com/arcprize/ARC-AGI-2) · [leaderboard](https://arcprize.org/leaderboard)

### GPQA
Answer 448 PhD-expert-written, 'Google-proof' multiple-choice questions in biology, physics, and chemistry that require deep multi-step scientific reasoning rather than retrievable facts. · **448 questions (198 in the GPQA-Diamond hardest subset) tasks**

> PhD experts reach ~65-74%, skilled non-experts only ~34% with web access. The GPQA-Diamond split is a standard reasoning headline metric reported in nearly every frontier model card (OpenAI, Anthropic, Google, etc.).

[paper](https://arxiv.org/abs/2311.12022) · [code](https://github.com/idavidrein/gpqa)

### FrontierMath
Solve original, unpublished research-level mathematics problems (number theory through algebraic geometry and category theory) that demand hours-to-days of expert reasoning and a verifiable final answer. · **Hundreds of original problems across Tiers 1-4 tasks**

> From Epoch AI; the hardest widely-cited math-reasoning benchmark, deliberately held out to prevent contamination (no public dataset repo). Frontier models solved <2% at launch; used as a top-line reasoning measure in recent frontier model releases.

[paper](https://arxiv.org/abs/2411.04872) · [leaderboard](https://epoch.ai/frontiermath)

### Humanity's Last Exam (HLE)
Answer 2,500 expert-vetted, frontier-of-knowledge questions across 100+ subjects (often multi-modal), each requiring expert-level multi-step reasoning to a closed-ended answer. · **2,500 questions across 100+ subjects tasks**

> From the Center for AI Safety and Scale AI; designed as the 'final' closed-ended academic exam. A standard frontier reasoning leaderboard now reported in model cards and run both with and without tool/agent access.

[paper](https://arxiv.org/abs/2501.14249) · [code](https://github.com/centerforaisafety/hle) · [leaderboard](https://agi.safe.ai/)

---

## Multi-Agent

*Collaboration, competition, and social/strategic interaction between agents.*

### SOTOPIA
Two LLM agents role-play assigned characters with private, sometimes-conflicting social goals across 90 scenarios (negotiation, collaboration, competition) and are scored on goal completion and relationship maintenance via multi-turn interactive social simulation. · **90 social scenarios tasks**

> ICLR 2024 spotlight; the de-facto standard for social/interactive multi-agent intelligence, widely cited and extended (SOTOPIA-pi, SOTOPIA-RL). SOTOPIA-Eval defines 7 social dimensions (BEL, REL, KNO, SEC, SOC, FIN, GOAL).

[paper](https://arxiv.org/abs/2310.11667) · [code](https://github.com/sotopia-lab/sotopia) · [leaderboard](https://huggingface.co/datasets/cmu-lti/sotopia)

### MultiAgentBench (MARBLE)
LLM agents must coordinate (and in some tasks compete) across eight tasks spanning research, software, gaming (Werewolf, Minecraft), database and web scenarios under different coordination topologies (star/chain/tree/graph), scored on milestone-based task and collaboration/competition KPIs. · **8 tasks / scenarios tasks**

> ACL 2025 Main. One of the most comprehensive purpose-built benchmarks for measuring both collaboration AND competition quality (not just task success) across coordination protocols; from UIUC's ulab.

[paper](https://arxiv.org/abs/2503.01935) · [code](https://github.com/MultiagentBench/MARBLE)

### BattleAgentBench
LLMs play a grid-based battle game across seven sub-stages of three difficulty tiers, requiring single-agent navigation, paired-agent cooperation, and multi-agent collaboration plus competition, giving a fine-grained measure of cooperative and competitive capability. · **7 sub-stages (3 difficulty levels) tasks**

> From Zhipu AI / Tsinghua (Jie Tang group); evaluated 11 LLMs. Frequently cited as a reference point for fine-grained cooperation-vs-competition evaluation in multi-agent systems.

[paper](https://arxiv.org/abs/2408.15971)

### AgentVerse
A multi-agent framework that dynamically assembles a group of expert LLM agents to collaboratively solve tasks (reasoning, coding, tool use, embodied), used to benchmark whether a coordinated group outperforms a single agent and to study emergent collaborative behaviors.

> ICLR 2024; a foundational and heavily-cited multi-agent collaboration framework from OpenBMB/Tsinghua, often used as a baseline that newer benchmarks (e.g. VillagerBench) compare against.

[paper](https://arxiv.org/abs/2308.10848) · [code](https://github.com/OpenBMB/AgentVerse)

### MetaGPT (SoftwareDev benchmark)
A multi-agent 'software company' assigns role-specialized LLM agents (PM, architect, engineer, QA) that collaborate via standardized operating procedures to turn a one-line requirement into a working codebase, benchmarked on HumanEval, MBPP, and the 70-task SoftwareDev dataset. · **70 SoftwareDev tasks (+ HumanEval/MBPP) tasks**

> ICLR 2024 oral; ~68k GitHub stars, one of the most influential multi-agent collaboration systems. Its SOP-based role collaboration and SoftwareDev eval are a canonical reference for collaborative agentic software engineering.

[paper](https://arxiv.org/abs/2308.00352) · [code](https://github.com/FoundationAgents/MetaGPT)

### AvalonBench
LLM agents play the hidden-role social-deduction game Resistance: Avalon, requiring deduction, teaming, deception, and persuasion among multiple agents, benchmarked against rule-based bots and other LLMs with ReAct-style role prompts. · **1 game (multiple roles) tasks**

> A widely-cited social-deduction multi-agent benchmark; commonly used to probe deception, hidden-information reasoning, and ad-hoc teamwork in LLM agents.

[paper](https://arxiv.org/abs/2310.05036) · [code](https://github.com/jonathanmli/Avalon-LLM)

### Werewolf Arena
Eight LLM players (Seer, Doctor, 2 Werewolves, 4 Villagers) compete in the Werewolf social-deduction game using a bidding-based dynamic turn-taking system, testing deception, deduction, and persuasion in an arena-style tournament between models. · **1 game (8 roles) tasks**

> From Google Research; a prominent case study in evaluating LLMs via social deduction, introducing the bidding turn-taking mechanism and arena tournament format between Gemini and GPT models.

[paper](https://arxiv.org/abs/2407.13943) · [code](https://github.com/google/werewolf_arena)

### GameBench
LLM agents play nine multiplayer strategy games spanning abstract strategy, hidden information, social deduction, language communication and cooperation, deliberately chosen to be absent from pretraining corpora, to cross-domain-benchmark strategic reasoning. · **9 games tasks**

> A cross-domain strategic-reasoning benchmark covering multi-agent competition, cooperation, and social deduction; useful for isolating reasoning skills from memorized strategy knowledge.

[paper](https://arxiv.org/abs/2406.06613) · [code](https://github.com/Joshuaclymer/GameBench) · [leaderboard](https://gamebench-website.vercel.app/)

### GAMA-Bench
LLMs act as players in eight classical multi-agent game-theory games (across cooperation, betrayal, and sequential settings) under a dynamic scoring scheme that quantitatively measures their decision-making robustness, generalizability, and strategy in multi-agent environments. · **8 game-theory games tasks**

> Game-theory-grounded benchmark for multi-agent decision-making (e.g. public goods, guessing games, auctions); from CUHK-ARISE, frequently cited for evaluating LLM rationality in N-agent settings.

[paper](https://arxiv.org/abs/2403.11807) · [code](https://github.com/CUHK-ARISE/GAMABench)

### Collab-Overcooked
Two LLM agents must cooperate in an extended Overcooked-AI kitchen environment, communicating in natural language to complete 30 open-ended cooking tasks, scored with process-oriented metrics that probe fine-grained collaboration (not just final success). · **30 open-ended tasks tasks**

> EMNLP 2025 Main; notable for process-oriented collaboration metrics that diagnose how (not just whether) agents coordinate, on the well-known Overcooked cooperation testbed.

[paper](https://arxiv.org/abs/2502.20073) · [code](https://github.com/YusaeMeow/Collab-Overcooked)

### CICERO / Diplomacy evaluation
An agent must play full-press Diplomacy: simultaneously negotiate, persuade, form and break alliances via free-form natural-language dialogue with six other players while executing strategic moves, evaluated by score and rank against human players in online games. · **1 game (7 players) tasks**

> Meta AI's landmark result: CICERO reached the top 10% of human Diplomacy players, combining a language model with strategic planning/RL. The canonical benchmark for combined negotiation + strategic multi-agent play; recent 'Democratizing Diplomacy' (arXiv:2508.07485) turns it into a reusable harness for any LLM.

[paper](https://arxiv.org/abs/2203.06647) · [code](https://github.com/facebookresearch/diplomacy_cicero)

---

## Science & Research

*Data analysis, ML engineering, and autonomous scientific discovery.*

### ScienceAgentBench
Given a real scientific data-analysis task, the agent must write a self-contained Python program that produces the correct result across bioinformatics, computational chemistry, GIS, and neuroscience. · **102 tasks**

> ICLR 2025; 102 tasks extracted from 44 peer-reviewed papers, validated by 9 domain experts. Widely cited reference benchmark for data-driven scientific discovery; best agents solve only ~32%.

[paper](https://arxiv.org/abs/2410.05080) · [code](https://github.com/OSU-NLP-Group/ScienceAgentBench) · [leaderboard](https://osu-nlp-group.github.io/ScienceAgentBench/)

### DiscoveryBench
Given one or more datasets and a discovery goal, the agent must derive a specific, supported hypothesis by running the full multi-step data-driven discovery workflow. · **264 real + 903 synthetic tasks**

> From Allen Institute for AI; first benchmark to formalize multi-step data-driven discovery across 6 domains derived from published papers. Best system scores ~25%.

[paper](https://arxiv.org/abs/2407.01725) · [code](https://github.com/allenai/discoverybench)

### PaperBench
Given an ICML 2024 paper, the agent must replicate it from scratch — understand the contributions, build the codebase, and run experiments to reproduce its empirical results. · **20 papers (8,316 gradable sub-tasks) tasks**

> OpenAI benchmark (ICML 2025) with author-co-designed rubrics; used in OpenAI model evaluations. Best agent (Claude 3.5 Sonnet) scored 21% vs 41% for PhD-level humans in 48h.

[paper](https://arxiv.org/abs/2504.01848) · [code](https://github.com/openai/frontier-evals)

### CORE-Bench
Given a published paper's code and data in a Docker environment, the agent must computationally reproduce the reported results and answer questions about them. · **270 tasks**

> Princeton; 270 tasks from 90 papers across CS, social science, and medicine at 3 difficulty levels. Hosted on the Holistic Agent Leaderboard (HAL); a standard reproducibility eval.

[paper](https://arxiv.org/abs/2409.11363) · [code](https://github.com/siegelz/core-bench) · [leaderboard](https://hal.cs.princeton.edu)

### MLAgentBench
Given a dataset and an ML task description, the agent must autonomously develop or improve an ML model by reading/writing files, running code, and inspecting outputs. · **13 tasks**

> Stanford (SNAP); end-to-end ML experimentation tasks from CIFAR-10 to BabyLM. An early, widely-cited agentic research benchmark; best agent (Claude 3 Opus) had 37.5% success rate.

[paper](https://arxiv.org/abs/2310.03302) · [code](https://github.com/snap-stanford/MLAgentBench)

### DSBench
Given realistic data-analysis and data-modeling tasks from Kaggle and ModelOff with long, multimodal, multi-table contexts, the agent must produce correct analyses and models end-to-end. · **540 (466 analysis + 74 modeling) tasks**

> ICLR 2025; tests data science agents in realistic settings with large data files. Best agent solved only 34% of analysis tasks, showing a large gap to human experts.

[paper](https://arxiv.org/abs/2409.07703) · [code](https://github.com/LiqiangJing/DSBench)

### BixBench
Given heterogeneous real biological datasets and an open-ended research question, the agent must perform multi-step computational analysis in a Jupyter environment and interpret the results. · **53 scenarios (296 questions) tasks**

> FutureHouse + ScienceMachine; derived from 60 real published bioinformatics notebooks. Frontier models (GPT-4o, Claude 3.5 Sonnet) reach only ~17% in open-answer mode.

[paper](https://arxiv.org/abs/2503.00096) · [code](https://github.com/Future-House/BixBench)

### ResearchBench
Given research components extracted from papers, the agent must perform inspiration retrieval, hypothesis composition, and hypothesis ranking to demonstrate scientific-discovery reasoning. · **1367+ tasks**

> ACL Findings 2026; first large-scale benchmark decomposing scientific discovery into sub-tasks across 12 disciplines with expert validation. Tests hypothesis generation, not just code.

[paper](https://arxiv.org/abs/2503.21248) · [code](https://github.com/ankitala/ResearchBench)

### MLE-bench
Given a real Kaggle competition (dataset + task), the agent must run the full ML engineering pipeline — data prep, model training, tuning — and produce a valid submission scored against human leaderboards. · **75 tasks**

> OpenAI (ICLR 2025 Oral); the standard ML-engineering agent benchmark, used in OpenAI and other model cards. o1-preview+AIDE reached Kaggle-bronze level on 16.9% of competitions.

[paper](https://arxiv.org/abs/2410.07095) · [code](https://github.com/openai/mle-bench)

### RE-Bench
Given open-ended ML research-engineering environments (e.g. fit a scaling law, optimize a GPU kernel), the agent must maximize a measurable score, benchmarked head-to-head against human experts. · **7 tasks**

> METR; directly compares frontier agents against 61 human experts on AI R&D automation. Central to frontier-AI safety/capability evaluations; agents beat humans at 2h but lag at longer budgets.

[paper](https://arxiv.org/abs/2411.15114) · [code](https://github.com/METR/ai-rd-tasks)

### SciCode
Given a real scientific research problem decomposed into subproblems, the agent must synthesize code that recalls domain knowledge, reasons, and passes scientist-written gold test cases. · **80 problems (338 subproblems) tasks**

> Scientist-curated across physics, math, materials, biology, chemistry. Extremely hard (best model ~4.6% fully solved); used in AstaBench and the Holistic Agent Leaderboard.

[paper](https://arxiv.org/abs/2407.13168) · [code](https://github.com/scicode-bench/SciCode) · [leaderboard](https://scicode-bench.github.io/)

### AstaBench
The agent must complete entire scientific research workflows — literature search, code execution, data analysis, and end-to-end discovery — within a standardized, reproducible research environment. · **2400+ across 11 benchmarks tasks**

> Allen Institute for AI (2025); a holistic suite whose leaderboard is the first to control for tools used and inference cost. Evaluated 57 agents; AI still far from solving research assistance.

[paper](https://arxiv.org/abs/2510.21652) · [code](https://github.com/allenai/asta-bench) · [leaderboard](https://allenai.org/asta/bench)

---

## Safety, Security & Robustness

*Prompt injection, harmful-tool refusal, and adversarial robustness.*

### AgentHarm
Given an explicitly malicious multi-step request (e.g. fraud, cybercrime, harassment), the tool-using agent must either refuse or, if jailbroken, the benchmark measures whether it still completes the harmful task end-to-end. · **110 base behaviors (440 with augmentations) across 11 harm categories, 104 tools tasks**

> De facto standard for agent harmfulness/jailbreak robustness; built by the UK AI Safety Institute, integrated into Inspect Evals, and widely cited in model safety cards and red-teaming work.

[paper](https://arxiv.org/abs/2410.09024) · [code](https://github.com/UKGovernmentBEIS/inspect_evals) · [leaderboard](https://huggingface.co/datasets/ai-safety-institute/AgentHarm)

### AgentDojo
In realistic environments (email client, e-banking, travel booking) the agent must complete legitimate user tasks while resisting prompt-injection instructions hidden in tool/data outputs that try to hijack its behavior. · **97 realistic tasks, 629 security test cases tasks**

> One of the most influential prompt-injection agent benchmarks; NeurIPS 2024 Datasets & Benchmarks; maintains a public leaderboard and is the standard testbed for injection attacks/defenses (CaMeL, StruQ, Meta SecAlign all report on it).

[paper](https://arxiv.org/abs/2406.13352) · [code](https://github.com/ethz-spylab/agentdojo) · [leaderboard](https://agentdojo.spylab.ai)

### InjecAgent
The tool-integrated agent processes content returned by tools that contains injected attacker instructions, and is scored on whether it executes attacks causing direct harm to the user or exfiltration of private data. · **1,054 test cases, 17 user tools, 62 attacker tools tasks**

> Early and widely-cited indirect-prompt-injection benchmark for agents (ACL 2024 Findings); commonly used as a baseline alongside AgentDojo.

[paper](https://arxiv.org/abs/2403.02691) · [code](https://github.com/uiuc-kang-lab/InjecAgent)

### ToolEmu
Using an LM-emulated tool sandbox, the agent executes high-stakes tasks and an LM safety evaluator quantifies risky failures (e.g. data leaks, financial loss) without needing real tool implementations. · **144 test cases over 36 toolkits (311 tools) tasks**

> Pioneering emulator-based agent risk framework (ICLR 2024 Spotlight); foundational reference for LM-as-sandbox and LM-as-safety-judge evaluation of tool-using agents.

[paper](https://arxiv.org/abs/2309.15817) · [code](https://github.com/ryoungj/ToolEmu)

### R-Judge
Given a multi-turn agent interaction record, the model must judge whether the agent's behavior was unsafe and identify the safety risk, testing risk awareness rather than content harmlessness. · **569 multi-turn records, 27 risk scenarios, 10 risk types tasks**

> Standard benchmark for agent safety-risk awareness / LLM-as-safety-judge (EMNLP 2024 Findings); frequently used to evaluate guardrail and judge models.

[paper](https://arxiv.org/abs/2401.10019) · [code](https://github.com/Lordog/R-Judge)

### Agent Security Bench (ASB)
Across 10 agent scenarios (e-commerce, finance, autonomous driving, etc.) the agent is subjected to formalized attacks (prompt injection, memory poisoning, Plan-of-Thought backdoor) and paired defenses, scored by attack success rate. · **~90,000 test cases; 10 scenarios, 400+ tools, 27 attack/defense methods tasks**

> Most comprehensive single framework formalizing agent attacks AND defenses; ~90,000 test cases; widely cited in agent-security surveys for covering injection, memory, and backdoor vectors together.

[paper](https://arxiv.org/abs/2410.02644) · [code](https://github.com/agiresearch/ASB)

### RedCode
A code agent is given prompts to execute or generate code, and is scored on whether it recognizes and refuses risky operations (RedCode-Exec) and whether it declines to produce harmful software (RedCode-Gen). · **4,050 execution instances + 160 generation prompts (~4,000+ total) tasks**

> Leading safety benchmark for code/coding agents (NeurIPS 2024 Datasets & Benchmarks); covers 25 vulnerability types across 8 domains with real Docker execution.

[paper](https://arxiv.org/abs/2411.07781) · [code](https://github.com/AI-secure/RedCode) · [leaderboard](https://redcode-agent.github.io/)

### SafeAgentBench
An embodied LLM agent in an interactive simulator (AI2-THOR-based) receives instructions covering explicit and implicit physical hazards and must plan and execute safely or reject dangerous tasks. · **750 tasks covering 10 hazards and 3 task types tasks**

> First comprehensive benchmark for safe task planning of embodied agents; exposes that the safest baseline rejects only ~10% of detailed hazardous tasks.

[paper](https://arxiv.org/abs/2412.13178) · [code](https://github.com/shengyin1224/SafeAgentBench)

### Agent-SafetyBench
Across hundreds of interactive tool environments the agent faces tasks spanning 8 safety-risk categories, and is scored on whether its behavior avoids unsafe outcomes across 10 common failure modes. · **2,000 test cases across 349 environments tasks**

> Broad, widely-cited agent safety benchmark from THU-CoAI; notable finding that none of 16 popular agents scored above 60% safety, attributing failures to weak robustness and risk awareness.

[paper](https://arxiv.org/abs/2412.14470) · [code](https://github.com/thu-coai/Agent-SafetyBench)

### ST-WebAgentBench
In realistic enterprise web environments, the agent must complete tasks while obeying attached safety/trust policies (user consent, robustness, etc.), scored by Completion-Under-Policy and policy-violation Risk Ratio. · **375 tasks carrying 3,057 ST policies tasks**

> First benchmark targeting safety AND trustworthiness of web agents for enterprise scenarios; introduces policy-compliance metrics now reused by later web-agent safety work.

[paper](https://arxiv.org/abs/2410.06703) · [code](https://github.com/segev-shlomov/ST-WebAgentBench) · [leaderboard](https://sites.google.com/view/st-webagentbench/home)

### SafeArena
A web agent operating in self-hosted WebArena sites is given matched safe and harmful tasks (misinformation, illegal activity, harassment, cybercrime, social bias) and is scored on its compliance with the harmful requests. · **500 tasks (250 safe + 250 harmful) across 5 harm categories tasks**

> First benchmark focused on deliberate misuse of autonomous web agents (McGill-NLP, 2025); has a public leaderboard and found GPT-4o completed ~35% of harmful tasks.

[paper](https://arxiv.org/abs/2503.04957) · [code](https://github.com/McGill-NLP/safearena) · [leaderboard](https://safearena.github.io/)

### VWA-Adv (Dissecting Adversarial Robustness of Multimodal LM Agents)
A multimodal web agent on VisualWebArena environments faces adversarial trigger images/text injected into pages (illusioning and goal-misdirection attacks) and is scored on whether it is pushed to a targeted adversarial action. · **200 adversarial tasks tasks**

> Key benchmark/study of adversarial robustness for vision-language web agents (ICLR 2025); curated 200 realistic adversarial tasks with an agent-robustness evaluation framework (ARE).

[paper](https://arxiv.org/abs/2406.12814) · [code](https://github.com/ChenWu98/agent-attack)

---

## General & Real-World Work

*Cross-domain office/company tasks that mirror real knowledge work.*

### GAIA
Answer 466 human-authored real-world assistant questions that require multi-step reasoning, web browsing, multimodality, and tool use, each with a single verifiable short answer. · **466 tasks**

> The canonical general-AI-assistant benchmark (FAIR/Meta, HuggingFace, AutoGPT). Humans score 92% vs ~15% for GPT-4+plugins at launch; widely cited and reported in model cards and agent frameworks.

[paper](https://arxiv.org/abs/2311.12983) · [code](https://github.com/aymeric-roucher/GAIA) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### Gaia2 (Meta Agents Research Environments / ARE)
Operate across 800 scenarios in 10 simulated 'universes' with 11 apps, handling asynchronous, evolving environments under time constraints, ambiguity, noise, and multi-agent collaboration. · **800 tasks**

> Meta's 2025 successor to GAIA built on the ARE platform; introduces dynamic/asynchronous environments measuring execution, search, adaptability, temporal reasoning, ambiguity, and multi-agent capabilities. Actively maintained leaderboard.

[paper](https://arxiv.org/abs/2509.17158) · [code](https://github.com/facebookresearch/meta-agents-research-environments) · [leaderboard](https://huggingface.co/spaces/meta-agents-research-environments/leaderboard)

### TheAgentCompany
Act as a digital worker inside a self-hosted simulated software company, browsing internal sites, writing code, running programs, and messaging simulated coworkers to complete consequential workplace tasks. · **175 tasks**

> Influential real-workplace benchmark (CMU et al.) with a self-contained GitLab/Plane/RocketChat/ownCloud environment; best agents complete only ~30% of full tasks. Public leaderboard and submission process.

[paper](https://arxiv.org/abs/2412.14161) · [code](https://github.com/TheAgentCompany/TheAgentCompany) · [leaderboard](https://the-agent-company.com/)

### AgentBench
Evaluate an LLM as an agent across 8 distinct interactive environments (OS, database, knowledge graph, card game, web shopping/browsing, etc.) in multi-turn open-ended settings. · **8 environments tasks**

> ICLR 2024; one of the earliest and most-cited multi-environment LLM-as-agent benchmarks (Tsinghua/THUDM), evaluated 27 LLMs and surfaced the closed-vs-open-source agent capability gap.

[paper](https://arxiv.org/abs/2308.03688) · [code](https://github.com/THUDM/AgentBench)

### WorkBench
Execute 690 common business tasks (email, calendar, analytics, CRM, project management) in a sandbox with five databases and 26 tools, judged by unique, unambiguous outcome states. · **690 tasks**

> Pioneered outcome-centric automated evaluation for workplace agents; best ReAct agent (GPT-4) solved only 43% of tasks, exposing wrong-action errors like emailing the wrong person.

[paper](https://arxiv.org/abs/2405.00823) · [code](https://github.com/olly-styles/WorkBench)

### TaskBench
Decompose a user instruction, select the right tools from a tool graph, and predict their parameters across multi-domain task-automation scenarios, scored stage-by-stage with TaskEval.

> Microsoft/Zhejiang/Fudan benchmark (part of the JARVIS/HuggingGPT line); introduced the Tool Graph + Back-Instruct methodology now widely reused for tool-use/agent planning evaluation.

[paper](https://arxiv.org/abs/2311.18760) · [code](https://github.com/microsoft/JARVIS/tree/main/taskbench)

### CRMArena / CRMArena-Pro
Perform expert-validated professional CRM tasks (service, sales, configure-price-quote) over a populated Salesforce org with tens of thousands of records, across single- and multi-turn interactions. · **19 task types (CRMArena-Pro) tasks**

> Salesforce AI Research's enterprise-grounded benchmark; widely cited finding that top agents reach only ~58% single-turn and drop to ~35% multi-turn success. CRMArena (arXiv:2411.02305) is the original; Pro is the expanded B2B/B2C version.

[paper](https://arxiv.org/abs/2505.18878) · [code](https://github.com/SalesforceAIResearch/CRMArena) · [leaderboard](https://huggingface.co/spaces/Salesforce/CRMArena-Leaderboard)

### ColBench (Collaborative Agent Benchmark)
Collaborate with a simulated human partner over multiple turns to solve realistic backend programming tasks (graded by unit tests) and frontend design tasks (graded by image similarity).

> Introduced with Meta's SWEET-RL paper as the first agent benchmark designed to validate multi-turn RL on reasoning-intensive collaborative human-AI tasks with low engineering overhead.

[paper](https://arxiv.org/abs/2503.15478) · [code](https://github.com/facebookresearch/sweet_rl)

### Terminal-Bench
Complete hard, realistic end-to-end command-line tasks in a sandboxed terminal — compiling code, configuring legacy systems, training models, security and data-science workflows — verified by execution. · **89 (Core v0.1.1) tasks**

> Stanford x Laude Institute (ICLR 2026); a heavily-used agentic-terminal leaderboard cited in frontier model cards, with active 1.0/2.0/2.1 and Hard versions tracked on multiple aggregator sites.

[paper](https://arxiv.org/abs/2601.11868) · [code](https://github.com/laude-institute/terminal-bench) · [leaderboard](https://www.tbench.ai/leaderboard)

### OSWorld
Drive a real Ubuntu/Windows/macOS computer via screenshots and GUI/CLI actions to complete 369 open-ended desktop and web tasks spanning multiple applications, evaluated by execution scripts. · **369 tasks**

> NeurIPS 2024; the standard real-computer-use benchmark (XLang Lab) referenced in Anthropic/OpenAI computer-use model cards. Humans solve >72% vs ~12% for early best models, with rapid leaderboard progress since.

[paper](https://arxiv.org/abs/2404.07972) · [code](https://github.com/xlang-ai/OSWorld) · [leaderboard](https://os-world.github.io/)

### AssistantBench
Solve 214 realistic, time-consuming open-web tasks (e.g. monitoring real-estate markets, finding nearby businesses) that require navigating live websites, with automatically verifiable answers. · **214 tasks**

> Allen Institute/Bar-Ilan/Penn benchmark for realistic web assistance; exposed that no model exceeded ~25 accuracy and SOTA web agents scored near zero, motivating the SeePlanAct agent.

[paper](https://arxiv.org/abs/2407.15711) · [code](https://github.com/oriyor/assistantbench) · [leaderboard](https://assistantbench.github.io/)

---

## Contributing

Add a benchmark if it is real, used, and verifiable.

- Include the paper and/or code URL. Verify both are live before submitting.
- One concrete sentence: what the agent actually has to do.
- Put it in the dimension it most belongs to. One entry per PR.

```markdown
### Benchmark Name
One sentence on what the agent must do. · **N tasks**

[paper](url) · [code](url) · [leaderboard](url)
```

---

*Maintained as part of [first-tree](https://github.com/unispark-inc/first-tree?ref=awesome-ai-agent-benchmarks) — shared context infrastructure for agent teams.*