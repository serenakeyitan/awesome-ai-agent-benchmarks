# Awesome AI Agent Benchmarks

A curated, dimension-organized index of **78 benchmarks** for evaluating LLM-based AI agents — coding, web, computer use, tool use, reasoning, multi-agent, science, safety, and real-world work.

Evaluating AI agents is hard: a single accuracy number rarely captures whether a system can fix a real GitHub issue, drive a live browser, recover from a prompt injection, or plan a trip under constraints. This list organizes the benchmarks that matter across **10 capability dimensions** — from the headline evals reported in every frontier model card (SWE-bench Verified, τ-bench, GAIA, OSWorld) to the frontier stress-tests where even the best agents score in the single digits. Each entry says what it actually tests, with links to the paper, code, and live leaderboard.

> Curated by the [first-tree](https://github.com/unispark-inc/first-tree?ref=awesome-ai-agent-benchmarks) team.

---

## Contents

- [The index (all benchmarks, by influence tier)](#the-index)
- [Coding & Software Engineering](#coding--software-engineering) (9)
- [Web Browsing & Navigation](#web-browsing--navigation) (9)
- [Computer Use (GUI / OS)](#computer-use-gui--os) (7)
- [Tool Use & Function Calling](#tool-use--function-calling) (7)
- [Reasoning & Planning](#reasoning--planning) (6)
- [Multi-Agent](#multi-agent) (6)
- [Science & Research](#science--research) (9)
- [Safety, Security & Robustness](#safety-security--robustness) (12)
- [Cybersecurity (Offensive)](#cybersecurity-offensive) (4)
- [General & Real-World Work](#general--real-world-work) (9)

---

## The index

Every benchmark, ranked by **influence tier**, then by GitHub stars. Tier reflects real-world adoption — Tier 1 are the evals reported in frontier model cards and used as the default for their capability; Tier 2 are widely used and on active leaderboards; Tier 3 are emerging or niche. (Stars marked `*` belong to a parent framework, not the benchmark alone, so they over-count influence — tier is the more honest signal.)

### Tier 1 — frontier model-card standard  (29)

| Benchmark | Dimension | What it tests | Tasks | Stars |
|---|---|---|---|---:|
| [Aider Polyglot](https://github.com/Aider-AI/aider) | Coding | Complete 225 hard Exercism exercises across C++, Go, Java, JavaS… | 225 | 46.6k* |
| [BFCL (Berkeley Function-Calling Leaderboard)](https://github.com/ShishirPatil/gorilla) | Tool Use | Given a natural-language request and a set of function/API schem… | thousands (V1-V4, ~3700+ across categories) | 12.9k* |
| [SWE-bench](https://github.com/SWE-bench/SWE-bench) | Coding | Given a real GitHub issue and the full repository, the agent mus… | 2294 | 5.2k |
| [SWE-bench Verified](https://github.com/SWE-bench/SWE-bench) | Coding | Same task as SWE-bench (resolve a real GitHub issue via a patch… | 500 | 5.2k |
| [SWE-bench Multimodal](https://github.com/SWE-bench/SWE-bench) | Coding | Resolve real GitHub issues in user-facing JavaScript repos where… | 619 | 5.2k |
| [BrowseComp](https://github.com/openai/simple-evals) | Web | Answer 'inverted' questions that require persistent, creative we… | 1266 | 4.5k* |
| [AgentBench](https://github.com/THUDM/AgentBench) | Reasoning | Operate as an autonomous agent across 8 distinct interactive env… | 8 environments | 3.5k |
| [OSWorld](https://github.com/xlang-ai/OSWorld) | Computer Use | Execute 369 open-ended real-computer tasks (file ops, desktop ap… | 369 | 3k |
| [Terminal-Bench](https://github.com/laude-institute/terminal-bench) | Coding | Autonomously complete hard, end-to-end tasks in a real command-l… | 89 | 2.4k |
| [MLE-bench](https://github.com/openai/mle-bench) | Science | Given a real Kaggle competition (dataset + task), the agent must… | 75 | 1.6k |
| [WebArena](https://github.com/web-arena-x/webarena) | Web | Complete high-level natural-language tasks (e-commerce, forums,… | 812 | 1.5k |
| [SWE-Lancer](https://github.com/openai/SWELancer-Benchmark) | Coding | Complete real paid Upwork freelance software-engineering tasks (… | 1488 | 1.4k |
| [tau-bench (τ-bench)](https://github.com/sierra-research/tau-bench) | Tool Use | The agent plays a customer-service rep that must converse with a… | 165 (115 retail + 50 airline) | 1.3k |
| [PaperBench](https://github.com/openai/frontier-evals) | Science | Given an ICML 2024 paper, the agent must replicate it from scrat… | 20 papers (8,316 gradable sub-tasks) | 1.2k |
| [WebVoyager](https://github.com/MinorJerry/WebVoyager) | Web | Complete end-to-end tasks on 15 live, high-traffic real websites… | 643 | 1.1k |
| [Mind2Web](https://github.com/OSU-NLP-Group/Mind2Web) | Web | Predict the correct action sequence (element selection + operati… | 2350 | 1k |
| [LiveCodeBench](https://github.com/LiveCodeBench/LiveCodeBench) | Coding | Solve competitive-programming problems continuously scraped from… | 1000+ | 888 |
| [AndroidWorld](https://github.com/google-research/android_world) | Computer Use | Complete 116 programmatic tasks across 20 real Android apps on a… | 116 | 800 |
| [TheAgentCompany](https://github.com/TheAgentCompany/TheAgentCompany) | General | Act as a digital worker inside a self-hosted simulated software… | 175 | 727 |
| [AgentDojo](https://github.com/ethz-spylab/agentdojo) | Safety | In realistic environments (email client, e-banking, travel booki… | 97 realistic tasks, 629 security test cases | 630 |
| [AgentHarm](https://github.com/UKGovernmentBEIS/inspect_evals) | Safety | Given an explicitly malicious multi-step request (e.g. fraud, cy… | 110 base behaviors (440 with augmentations) across 11 harm categories, 104 tools | 551 |
| [VisualWebArena](https://github.com/web-arena-x/visualwebarena) | Web | Solve realistic visually-grounded web tasks (image-text inputs,… | 910 | 481 |
| [PlanBench](https://github.com/karthikv792/LLMs-Planning) | Reasoning | Generate and reason about plans in classical IPC planning domain… | ~26,250 prompts across multiple plan-reasoning task types | 466 |
| [CyberGym](https://github.com/sunblaze-ucb/cybergym) | Cybersecurity | Tasks agents with finding and exploiting real software vulnerabi… | 1,507 real vulnerabilities | 431 |
| [SOTOPIA](https://github.com/sotopia-lab/sotopia) | Multi-Agent | Two LLM agents role-play assigned characters with private, somet… | 90 social scenarios | 312 |
| [CyBench](https://github.com/andyzorigin/cybench) | Cybersecurity | Evaluates agents on 40 professional-level Capture-the-Flag (CTF)… | 40 CTF tasks | 266 |
| [SciCode](https://github.com/scicode-bench/SciCode) | Science | Given a real scientific research problem decomposed into subprob… | 80 problems (338 subproblems) | 208 |
| [InjecAgent](https://github.com/uiuc-kang-lab/InjecAgent) | Safety | The tool-integrated agent processes content returned by tools th… | 1,054 test cases, 17 user tools, 62 attacker tools | 144 |
| [GAIA](https://arxiv.org/abs/2311.12983) | Web | Answer real-world assistant questions that require multi-step re… | 466 | — |

### Tier 2 — widely used  (20)

| Benchmark | Dimension | What it tests | Tasks | Stars |
|---|---|---|---|---:|
| [ToolBench (ToolLLM)](https://github.com/OpenBMB/ToolBench) | Tool Use | Given user instructions, the agent must select and chain calls a… | 16,464 APIs / 3,451 tools; ~126k instruction-solution pairs | 5.7k* |
| [API-Bank](https://github.com/AlibabaResearch/DAMO-ConvAI/tree/main/api-bank) | Tool Use | A runnable benchmark where the agent must plan, retrieve, and ca… | 73 APIs, 314 dialogues, 753 API calls (eval set) | 1.6k |
| [Agents' Last Exam (ALE)](https://github.com/rdi-berkeley/agents-last-exam) | General | Asks agents to perform economically valuable, expert-sourced wor… | 1,500+ across 55 occupations | 721 |
| [TravelPlanner](https://github.com/OSU-NLP-Group/TravelPlanner) | Reasoning | Act as a travel-planning agent that queries a sandbox of ~4M rec… | 1,225 planning queries with reference plans | 523 |
| [BigCodeBench](https://github.com/bigcode-project/bigcodebench) | Coding | Write Python functions that correctly compose multiple library/A… | 1140 | 509 |
| [AgentBoard](https://github.com/hkust-nlp/AgentBoard) | Reasoning | Run an LLM agent through 9 multi-turn, partially-observable task… | 9 tasks across 1013 environments | 420 |
| [Multi-SWE-bench](https://github.com/multi-swe-bench/multi-swe-bench) | Coding | Resolve real GitHub issues via patches that pass hidden tests, b… | 1632 | 341 |
| [CVE-Bench](https://github.com/uiuc-kang-lab/cve-bench) | Cybersecurity | Tests whether an agent can exploit real-world web-application vu… | 40 CVEs | 240 |
| [AgentPoison](https://github.com/AI-secure/AgentPoison) | Safety | Red-teams a RAG/memory-augmented LLM agent by poisoning its know… | <0.1% poison rate, 80%+ attack success | 222 |
| [Online-Mind2Web](https://github.com/OSU-NLP-Group/Online-Mind2Web) | Web | Execute 300 realistic tasks on 136 live websites in an online se… | 300 | 182 |
| [DiscoveryBench](https://github.com/allenai/discoverybench) | Science | Given one or more datasets and a discovery goal, the agent must… | 264 real + 903 synthetic | 148 |
| [ScienceAgentBench](https://github.com/OSU-NLP-Group/ScienceAgentBench) | Science | Given a real scientific data-analysis task, the agent must write… | 102 | 141 |
| [BixBench](https://github.com/Future-House/BixBench) | Science | Given heterogeneous real biological datasets and an open-ended r… | 53 scenarios (296 questions) | 124 |
| [R-Judge](https://github.com/Lordog/R-Judge) | Safety | Given a multi-turn agent interaction record, the model must judg… | 569 multi-turn records, 27 risk scenarios, 10 risk types | 105 |
| [RedCode](https://github.com/AI-secure/RedCode) | Safety | A code agent is given prompts to execute or generate code, and i… | 4,050 execution instances + 160 generation prompts (~4,000+ total) | 82 |
| [CORE-Bench](https://github.com/siegelz/core-bench) | Science | Given a published paper's code and data in a Docker environment,… | 270 | 77 |
| [AssistantBench](https://github.com/oriyor/assistantbench) | Web | Solve realistic, time-consuming open-web tasks (e.g. 'which near… | 214 | 71 |
| [OS-Harm](https://github.com/tml-epfl/os-harm) | Safety | Measures the safety of computer-use (GUI) agents across 150 task… | 150 | 67 |
| [NATURAL PLAN](https://github.com/google-deepmind/natural-plan) | Reasoning | Solve natural-language planning problems in Trip Planning, Meeti… | 3 task families (Trip, Meeting, Calendar planning) | 57 |
| [BountyBench](https://github.com/cybench/BountyBench) | Cybersecurity | Grounds agent cyber capability in real money: 25 real systems an… | 25 systems, 40 bounties | 9 |

### Tier 3 — emerging / niche  (19)

| Benchmark | Dimension | What it tests | Tasks | Stars |
|---|---|---|---|---:|
| [CICERO / Diplomacy evaluation](https://github.com/facebookresearch/diplomacy_cicero) | Multi-Agent | An agent must play full-press Diplomacy: simultaneously negotiat… | 1 game (7 players) | 1.4k |
| [tau2-bench (τ²-bench)](https://github.com/sierra-research/tau2-bench) | Tool Use | Extends tau-bench to dual-control settings where both the agent… | hundreds across telecom/retail/airline | 1.4k |
| [WindowsAgentArena (WAA)](https://github.com/microsoft/WindowsAgentArena) | Computer Use | Complete 154 multi-step Windows-OS tasks across real apps (Offic… | 154 | 874 |
| [MCP-Universe](https://github.com/SalesforceAIResearch/MCP-Universe) | Tool Use | The agent connects to 11 real, live Model Context Protocol (MCP)… | 231 | 592 |
| [Gaia2 (Meta Agents Research Environments / ARE)](https://github.com/facebookresearch/meta-agents-research-environments) | General | Operate across 800 scenarios in 10 simulated 'universes' with 11… | 800 | 522 |
| [ScreenSpot-Pro](https://github.com/likaixin2000/ScreenSpot-Pro-GUI-Grounding) | Computer Use | Locate tiny, cluttered UI targets from instructions on ultra-hig… | 1581 | 378 |
| [Agent Security Bench (ASB)](https://github.com/agiresearch/ASB) | Safety | Across 10 agent scenarios (e-commerce, finance, autonomous drivi… | ~90,000 test cases; 10 scenarios, 400+ tools, 27 attack/defense methods | 264 |
| [ToolSandbox](https://github.com/apple/ToolSandbox) | Tool Use | A stateful, conversational benchmark with an on-policy LLM user… | 1032 test scenarios | 261 |
| [WorkArena / WorkArena++](https://github.com/ServiceNow/WorkArena) | Web | Perform common enterprise knowledge-work tasks on the live Servi… | 33 tasks / 19,912 instances (WorkArena L1); 682 (WorkArena++) | 256 |
| [Agent-SafetyBench](https://github.com/thu-coai/Agent-SafetyBench) | Safety | Across hundreds of interactive tool environments the agent faces… | 2,000 test cases across 349 environments | 144 |
| [RE-Bench](https://github.com/METR/ai-rd-tasks) | Science | Given open-ended ML research-engineering environments (e.g. fit… | 7 | 141 |
| [CRMArena / CRMArena-Pro](https://github.com/SalesforceAIResearch/CRMArena) | General | Perform expert-validated professional CRM tasks (service, sales,… | 19 task types (CRMArena-Pro) | 141 |
| [AstaBench](https://github.com/allenai/asta-bench) | Science | The agent must complete entire scientific research workflows — l… | 2400+ across 11 benchmarks | 111 |
| [GAMA-Bench](https://github.com/CUHK-ARISE/GAMABench) | Multi-Agent | LLMs act as players in eight classical multi-agent game-theory g… | 8 game-theory games | 97 |
| [MultiAgentBench (MARBLE)](https://github.com/MultiagentBench/MARBLE) | Multi-Agent | LLM agents must coordinate (and in some tasks compete) across ei… | 8 tasks / scenarios | 51 |
| [Werewolf Arena](https://github.com/google/werewolf_arena) | Multi-Agent | Eight LLM players (Seer, Doctor, 2 Werewolves, 4 Villagers) comp… | 1 game (8 roles) | 48 |
| [OpenAgentSafety](https://github.com/sani903/OpenAgentSafety) | Safety | Evaluates agent safety in realistic multi-tool environments acro… | 350+ | 38 |
| [Collab-Overcooked](https://github.com/YusaeMeow/Collab-Overcooked) | Multi-Agent | Two LLM agents must cooperate in an extended Overcooked-AI kitch… | 30 open-ended tasks | 35 |
| [SafeArena](https://github.com/McGill-NLP/safearena) | Safety | A web agent operating in self-hosted WebArena sites is given mat… | 500 tasks (250 safe + 250 harmful) across 5 harm categories | 23 |

<sub>`*` = star count is for the parent framework/repo, not the benchmark alone.</sub>

---

## Coding & Software Engineering

*Resolving real issues, writing code, building libraries, working in the terminal.*

### Aider Polyglot `T1`
Complete 225 hard Exercism exercises across C++, Go, Java, JavaScript, Python and Rust, applying edits in a specified diff format with one retry shown unit-test feedback. · **225 tasks**

> Highly influential practitioner benchmark from the Aider project; measures both correctness and whether models can edit code in the right format. Frequently cited in frontier-model launches.

[code](https://github.com/Aider-AI/aider) · [leaderboard](https://aider.chat/docs/leaderboards/)

### SWE-bench `T1`
Given a real GitHub issue and the full repository, the agent must produce a code patch (diff) that resolves the issue and passes the repo's hidden test suite. · **2294 tasks**

> The foundational real-world software-engineering benchmark (ICLR 2024, Princeton). 2,294 tasks across 12 Python repos. Cited everywhere and the basis for most agentic coding evals and model cards.

[paper](https://arxiv.org/abs/2310.06770) · [code](https://github.com/SWE-bench/SWE-bench) · [leaderboard](https://www.swebench.com/)

### SWE-bench Verified `T1`
Same task as SWE-bench (resolve a real GitHub issue via a patch that passes hidden tests), but on a 500-instance human-validated subset where problems are confirmed solvable and tests are correct. · **500 tasks**

> The de facto industry-standard coding-agent metric, built with OpenAI human annotators. Headline number in nearly every frontier-model release (Claude, GPT, Gemini) and the most-watched coding leaderboard.

[paper](https://arxiv.org/abs/2310.06770) · [code](https://github.com/SWE-bench/SWE-bench) · [leaderboard](https://www.swebench.com/verified.html)

### SWE-bench Multimodal `T1`
Resolve real GitHub issues in user-facing JavaScript repos where the problem statement or tests include images (UI bugs, data-viz, mapping), requiring visual reasoning plus code editing. · **619 tasks**

> First benchmark testing coding agents on visual/front-end software domains; 619 tasks from 17 JS repos. Top systems resolve only ~12%, exposing a large gap beyond text-only Python tasks.

[paper](https://arxiv.org/abs/2410.03859) · [code](https://github.com/SWE-bench/SWE-bench)

### Terminal-Bench `T1`
Autonomously complete hard, end-to-end tasks in a real command-line environment (compiling code, training models, configuring servers, sysadmin, security) verified by automated checks. · **89 tasks**

> Stanford / Laude Institute benchmark for terminal/CLI agents; widely adopted across scaffolds (Codex CLI, OpenHands, Aider, Claude Code). v2.0 evaluates 89 tasks with multiple trials and 100+ agents on the leaderboard.

[code](https://github.com/laude-institute/terminal-bench) · [leaderboard](https://www.tbench.ai/leaderboard)

### SWE-Lancer `T1`
Complete real paid Upwork freelance software-engineering tasks (bug fixes to feature builds) graded by end-to-end tests, plus managerial tasks choosing between implementation proposals. · **1488 tasks**

> OpenAI benchmark of 1,400+ tasks worth $1M in real payouts; maps model performance to dollar value. The leading economically-grounded real-world SWE benchmark, used in OpenAI model evaluations.

[paper](https://arxiv.org/abs/2502.12115) · [code](https://github.com/openai/SWELancer-Benchmark)

### LiveCodeBench `T1`
Solve competitive-programming problems continuously scraped from LeetCode, AtCoder and Codeforces, with code generation plus self-repair, code execution, and test-output prediction. · **1000+ tasks**

> The standard contamination-free code-generation benchmark; problems are date-stamped so models are scored only on problems released after their training cutoff. Widely cited and used in model cards.

[paper](https://arxiv.org/abs/2403.07974) · [code](https://github.com/LiveCodeBench/LiveCodeBench)

### BigCodeBench `T2`
Write Python functions that correctly compose multiple library/API calls (139 libraries, 7 domains) to satisfy complex natural-language instructions, verified by rich test cases. · **1140 tasks**

> ICLR 2025; the leading benchmark for realistic library-heavy coding (1,140 tasks, 723 function calls). Best LLMs reach ~60% vs 97% human, making it a hard, widely-used signal beyond toy code generation.

[paper](https://arxiv.org/abs/2406.15877) · [code](https://github.com/bigcode-project/bigcodebench) · [leaderboard](https://bigcode-bench.github.io/)

### Multi-SWE-bench `T2`
Resolve real GitHub issues via patches that pass hidden tests, but across 7 non-Python languages (Java, TypeScript, JavaScript, Go, Rust, C, C++). · **1632 tasks**

> First large multilingual issue-resolving benchmark (ByteDance Seed), 1,632 issues. Increasingly used to show coding agents generalize beyond Python.

[paper](https://arxiv.org/abs/2504.02605) · [code](https://github.com/multi-swe-bench/multi-swe-bench)

---

## Web Browsing & Navigation

*Driving live or cloned websites: shopping, research, form-filling, multi-step navigation.*

### BrowseComp `T1`
Answer 'inverted' questions that require persistent, creative web browsing to locate hard-to-find, entangled facts, with short answers that are easy to verify against references. · **1266 tasks**

> OpenAI (2025); the reference benchmark for deep-research / persistent-browsing agents, used in OpenAI Deep Research and frontier-model model cards. Designed so answers take humans 10+ minutes and aren't on page one of Google.

[paper](https://arxiv.org/abs/2504.12516) · [code](https://github.com/openai/simple-evals) · [leaderboard](https://llm-stats.com/benchmarks/browsecomp)

### WebArena `T1`
Complete high-level natural-language tasks (e-commerce, forums, GitLab, CMS) end-to-end in self-hosted, fully-functional clones of real websites, scored by execution-based functional correctness. · **812 tasks**

> The canonical reproducible web-agent benchmark (ICLR 2024); GPT-4 baseline ~14% vs human ~78%. Widely cited and used in frontier-model agent evals; ServiceNow released WebArena-Verified (2025) as an audited version.

[paper](https://arxiv.org/abs/2307.13854) · [code](https://github.com/web-arena-x/webarena) · [leaderboard](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ)

### WebVoyager `T1`
Complete end-to-end tasks on 15 live, high-traffic real websites (Amazon, Booking, Google Maps, GitHub, etc.) using screenshots + accessibility tree, scored by a GPT-4V automatic judge. · **643 tasks**

> ACL 2024; one of the most-cited 'agent on the live web' benchmarks and a de-facto standard for multimodal browsing agents. Its GPT-4V auto-eval (~85% agreement with humans) is widely reused.

[paper](https://arxiv.org/abs/2401.13919) · [code](https://github.com/MinorJerry/WebVoyager)

### Mind2Web `T1`
Predict the correct action sequence (element selection + operation) to complete open-ended tasks across 137 real websites from offline interaction traces, testing cross-domain/website generalization. · **2350 tasks**

> NeurIPS 2023 Spotlight; the first benchmark for generalist web agents and a foundational dataset spanning 31 domains / 137 sites. Heavily used for training and offline action-prediction evaluation.

[paper](https://arxiv.org/abs/2306.06070) · [code](https://github.com/OSU-NLP-Group/Mind2Web) · [leaderboard](https://osu-nlp-group.github.io/Mind2Web/)

### VisualWebArena `T1`
Solve realistic visually-grounded web tasks (image-text inputs, spatial reasoning) on self-hosted Classifieds, Shopping, and Reddit sites, evaluated by execution-based correctness. · **910 tasks**

> ACL 2024 multimodal extension of WebArena; the standard test for vision-grounded web agents. Top agents reached ~16% vs human ~89%, exposing a large multimodal gap.

[paper](https://arxiv.org/abs/2401.13649) · [code](https://github.com/web-arena-x/visualwebarena) · [leaderboard](https://jykoh.com/vwa)

### GAIA `T1`
Answer real-world assistant questions that require multi-step reasoning, tool use, and web browsing to find and synthesize information, with short verifiable answers. · **466 tasks**

> Meta/HuggingFace/AutoGPT benchmark; the most prominent general-assistant eval where web browsing is core. Humans ~92% vs GPT-4+plugins ~15%. Heavily used in agent framework papers and model cards; its web subset is reused in WebVoyager.

[paper](https://arxiv.org/abs/2311.12983) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### Online-Mind2Web `T2`
Execute 300 realistic tasks on 136 live websites in an online setting, judged by the WebJudge LLM-as-a-judge protocol, to measure true end-to-end success rather than offline action matching. · **300 tasks**

> COLM 2025 ('An Illusion of Progress?'); a current, widely-cited live-web benchmark used by browser-use and frontier labs. Showed prior results were over-optimistic (OpenAI Operator ~61%). WebJudge auto-eval ~85% human agreement.

[paper](https://arxiv.org/abs/2504.01382) · [code](https://github.com/OSU-NLP-Group/Online-Mind2Web) · [leaderboard](https://huggingface.co/datasets/osunlp/Online-Mind2Web)

### AssistantBench `T2`
Solve realistic, time-consuming open-web tasks (e.g. 'which nearby gyms have weekend classes before 7AM?') that require browsing many pages across hundreds of real sites and returning a precise answer. · **214 tasks**

> EMNLP 2024; a hard open-web information-seeking benchmark (525+ pages across 258 sites) where no system exceeds ~26 points. Integrated into BrowserGym and used to probe long-horizon browsing.

[paper](https://arxiv.org/abs/2407.15711) · [code](https://github.com/oriyor/assistantbench) · [leaderboard](https://huggingface.co/spaces/AssistantBench/leaderboard)

### WorkArena / WorkArena++ `T3`
Perform common enterprise knowledge-work tasks on the live ServiceNow platform (filtering lists, filling forms, service catalog, dashboards, menu navigation), plus compositional multi-step tasks in WorkArena++. · **33 tasks / 19,912 instances (WorkArena L1); 682 (WorkArena++) tasks**

> ICML 2024 (L1) and NeurIPS 2024 (WorkArena++); the leading enterprise/UI web-agent benchmark, integrated into BrowserGym. Best agents only ~55%, highlighting enterprise-software difficulty.

[paper](https://arxiv.org/abs/2403.07718) · [code](https://github.com/ServiceNow/WorkArena) · [leaderboard](https://servicenow.github.io/WorkArena/)

---

## Computer Use (GUI / OS)

*Operating real desktops, mobile, and GUI apps via screenshots and clicks.*

### OSWorld `T1`
Execute 369 open-ended real-computer tasks (file ops, desktop apps, web, multi-app workflows) in a live Ubuntu/Windows VM, scored by execution-based checks on final system state. · **369 tasks**

> The de facto standard for desktop computer-use agents. Used in model cards/blogs by Anthropic, OpenAI, and others; OSWorld-Verified is the canonical leaderboard. Human ~72% vs early agents ~12%, now ~60%+.

[paper](https://arxiv.org/abs/2404.07972) · [code](https://github.com/xlang-ai/OSWorld) · [leaderboard](https://os-world.github.io/)

### WebArena `T1`
Complete 812 long-horizon web tasks (shopping, GitLab, Reddit-style forum, CMS, maps) in fully functional self-hosted web apps, scored by functional correctness of the end state. · **812 tasks**

> The dominant reproducible web-agent benchmark; dozens of agents compete on its leaderboard. Human ~78% vs original GPT-4 agent ~14%, now 70%+.

[paper](https://arxiv.org/abs/2307.13854) · [code](https://github.com/web-arena-x/webarena) · [leaderboard](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ)

### WebVoyager `T1`
Drive a real browser end-to-end against 15 live production websites (Amazon, Google Flights, BBC, etc.) to complete 643 real-world tasks, auto-evaluated by a GPT-4V judge over the screenshot trajectory. · **643 tasks**

> Widely-used live-web multimodal agent benchmark; popularized the screenshot-based browsing agent and the VLM-as-judge evaluation protocol (85% agreement with humans).

[paper](https://arxiv.org/abs/2401.13919) · [code](https://github.com/MinorJerry/WebVoyager)

### Mind2Web `T1`
Predict the correct action sequence (element selection + operation) to complete 2,000+ crowd-sourced open-ended tasks across 137 real websites spanning 31 domains. · **2350 tasks**

> NeurIPS 2023 Spotlight; the first generalist-web-agent benchmark and a foundational dataset for training/evaluating web action-prediction models, very heavily cited.

[paper](https://arxiv.org/abs/2306.06070) · [code](https://github.com/OSU-NLP-Group/Mind2Web)

### AndroidWorld `T1`
Complete 116 programmatic tasks across 20 real Android apps on a live emulator, with dynamically randomized parameters yielding millions of task variations and reward signals. · **116 tasks**

> Google Research's reference benchmark for mobile/GUI agents; widely cited and used in mobile-agent model evals. Human ~80% vs early M3A agent ~30.6%.

[paper](https://arxiv.org/abs/2405.14573) · [code](https://github.com/google-research/android_world) · [leaderboard](https://google-research.github.io/android_world/)

### WindowsAgentArena (WAA) `T3`
Complete 154 multi-step Windows-OS tasks across real apps (Office, VS Code, Edge, File Explorer, Settings, Paint) in parallelizable Docker/Azure VMs with execution-based evaluation. · **154 tasks**

> Microsoft's Windows analogue to OSWorld; built on the OSWorld framework. Heavily used for benchmarking enterprise/desktop agents; full eval runs in ~20 min via Azure parallelization.

[paper](https://arxiv.org/abs/2409.08264) · [code](https://github.com/microsoft/WindowsAgentArena)

### ScreenSpot-Pro `T3`
Locate tiny, cluttered UI targets from instructions on ultra-high-resolution professional desktop software (CAD, IDEs, office, scientific) via 1,581 expert-annotated screenshot-instruction pairs. · **1581 tasks**

> The hard, high-resolution successor to ScreenSpot; targets average 0.07% of screen area. Standard stress-test for grounding models (best model ~18.9% at release).

[paper](https://arxiv.org/abs/2504.07981) · [code](https://github.com/likaixin2000/ScreenSpot-Pro-GUI-Grounding) · [leaderboard](https://gui-agent.github.io/grounding-leaderboard/)

---

## Tool Use & Function Calling

*Calling APIs and tools correctly, multi-turn, with the right arguments.*

### BFCL (Berkeley Function-Calling Leaderboard) `T1`
Given a natural-language request and a set of function/API schemas, the agent must emit syntactically correct function calls (single, parallel, multiple, multi-turn, and agentic) that an AST/state checker validates for correctness. · **thousands (V1-V4, ~3700+ across categories) tasks**

> The de-facto industry standard for function-calling evaluation; cited in nearly every model card (OpenAI, Anthropic, Google, Mistral, etc.). V3 added multi-turn/multi-step and V4 (2025) added real-world agentic tasks with web search, memory, and format-sensitivity.

[paper](https://proceedings.mlr.press/v267/patil25a.html) · [code](https://github.com/ShishirPatil/gorilla) · [leaderboard](https://gorilla.cs.berkeley.edu/leaderboard.html)

### tau-bench (τ-bench) `T1`
The agent plays a customer-service rep that must converse with an LLM-simulated user while calling domain APIs (retail, airline) under written policy constraints, judged by the final database state plus a pass^k consistency metric. · **165 (115 retail + 50 airline) tasks**

> From Sierra (Bret Taylor); the most influential tool-agent-user interaction benchmark. Heavily used in frontier model cards (Anthropic, OpenAI) as the canonical agentic tool-use eval; pass^k exposes reliability gaps.

[paper](https://arxiv.org/abs/2406.12045) · [code](https://github.com/sierra-research/tau-bench) · [leaderboard](https://www.taubench.com/)

### ToolBench (ToolLLM) `T2`
Given user instructions, the agent must select and chain calls across 16,000+ real RapidAPI REST APIs (single-tool and multi-tool, with DFSDT solution paths), evaluated by pass rate and win rate against a reference. · **16,464 APIs / 3,451 tools; ~126k instruction-solution pairs tasks**

> ICLR'24 spotlight from OpenBMB; the foundational large-scale real-API tool-learning benchmark and the most-cited baseline for massive-toolset agents. Spawned StableToolBench and many follow-ups.

[paper](https://arxiv.org/abs/2307.16789) · [code](https://github.com/OpenBMB/ToolBench)

### API-Bank `T2`
A runnable benchmark where the agent must plan, retrieve, and call from a pool of 73 executable APIs across multi-turn tool-use dialogues, scored on correct API calls and response quality. · **73 APIs, 314 dialogues, 753 API calls (eval set) tasks**

> EMNLP 2023; one of the earliest and most-cited tool-augmented-LLM benchmarks with a runnable evaluation system, frequently used as a baseline for planning/retrieval/calling abilities.

[paper](https://arxiv.org/abs/2304.08244) · [code](https://github.com/AlibabaResearch/DAMO-ConvAI/tree/main/api-bank)

### tau2-bench (τ²-bench) `T3`
Extends tau-bench to dual-control settings where both the agent AND the simulated user can call tools (modeled as a Dec-POMDP), with a Telecom troubleshooting domain plus retail and airline and a compositional task generator. · **hundreds across telecom/retail/airline tasks**

> The 2025 successor to tau-bench; now the headline conversational tool-use eval reported in current frontier model launches. Adds collaborative dual-control troubleshooting that single-agent benchmarks miss.

[paper](https://arxiv.org/abs/2506.07982) · [code](https://github.com/sierra-research/tau2-bench) · [leaderboard](https://www.taubench.com/)

### MCP-Universe `T3`
The agent connects to 11 real, live Model Context Protocol (MCP) servers across 6 domains (maps, GitHub repo management, finance, 3D design, browser automation, web search) and must discover unknown tools and complete long-horizon real-world tasks with execution-based grading. · **231 tasks**

> From Salesforce AI Research (2025); the first comprehensive benchmark over real running MCP servers, now a key reference for evaluating agents on the live MCP ecosystem (even top models like GPT-5 score under 50%).

[paper](https://arxiv.org/abs/2508.14704) · [code](https://github.com/SalesforceAIResearch/MCP-Universe) · [leaderboard](https://mcp-universe.github.io/)

### ToolSandbox `T3`
A stateful, conversational benchmark with an on-policy LLM user simulator where tools mutate shared world state and have implicit inter-tool dependencies, scored via milestone/minefield checks over the trajectory. · **1032 test scenarios tasks**

> From Apple; one of the most-cited benchmarks targeting stateful tool execution and state-dependency/canonicalization challenges that stateless single-turn benchmarks ignore.

[paper](https://arxiv.org/abs/2408.04682) · [code](https://github.com/apple/ToolSandbox)

---

## Reasoning & Planning

*Multi-step problem solving, planning under constraints, hard knowledge.*

### AgentBench `T1`
Operate as an autonomous agent across 8 distinct interactive environments (OS, database, knowledge graph, card game, lateral-thinking puzzles, web shopping/browsing, household) over multiple turns of reasoning and decision-making. · **8 environments tasks**

> ICLR'24; the first benchmark to systematically evaluate LLM-as-agent across diverse environments. Tested 27+ models and showed poor long-term reasoning/decision-making is the main blocker for usable agents. Heavily cited foundational agent benchmark from Tsinghua (THUDM).

[paper](https://arxiv.org/abs/2308.03688) · [code](https://github.com/THUDM/AgentBench) · [leaderboard](https://docs.google.com/spreadsheets/d/e/2PACX-1vRR3Wl7wsCgHpwUw1_eUXW_fptAPLL3FkhnW_rua0O1Ji_GIVrpTjY5LaKAhwO-WeARjnY_KNw0SYNJ/pubhtml)

### PlanBench `T1`
Generate and reason about plans in classical IPC planning domains (Blocksworld, Logistics), including obfuscated variants, to test true planning vs. memorized common-sense retrieval. · **~26,250 prompts across multiple plan-reasoning task types tasks**

> NeurIPS 2023 Datasets & Benchmarks; the standard reference for rigorous, automated-planning-grounded evaluation of LLM planning. Exposed large gaps that persisted even with reasoning models (o1 analysis), making it a touchstone in the LLM-planning literature.

[paper](https://arxiv.org/abs/2206.10498) · [code](https://github.com/karthikv792/LLMs-Planning)

### GAIA `T1`
Answer 466 real-world questions that each require a chained sequence of reasoning, web browsing, multi-modality handling, and tool use to reach a single unambiguous answer. · **466 questions (300 held out for the leaderboard, 3 difficulty levels) tasks**

> The canonical general-assistant agent benchmark from Meta AI/HuggingFace; humans score ~92% vs ~15% for GPT-4+plugins at release. Widely used in model cards and agent frameworks; also mirrored on the HAL (Princeton) leaderboard.

[paper](https://arxiv.org/abs/2311.12983) · [code](https://huggingface.co/datasets/gaia-benchmark/GAIA) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### TravelPlanner `T2`
Act as a travel-planning agent that queries a sandbox of ~4M records via tools and produces a complete multi-day itinerary satisfying many hard and soft real-world constraints. · **1,225 planning queries with reference plans tasks**

> ICML'24 Spotlight (OSU NLP); the marquee real-world constrained-planning agent benchmark. GPT-4 reached only 0.6% final-pass rate at release, making it a hard, widely-cited stress test for tool-use + constraint planning.

[paper](https://arxiv.org/abs/2402.01622) · [code](https://github.com/OSU-NLP-Group/TravelPlanner) · [leaderboard](https://huggingface.co/spaces/osunlp/TravelPlannerLeaderboard)

### AgentBoard `T2`
Run an LLM agent through 9 multi-turn, partially-observable task families (embodied AI, games, web, tool use) and score fine-grained progress rate rather than only final success. · **9 tasks across 1013 environments tasks**

> NeurIPS 2024 Oral (HKUST NLP). Introduced the influential per-step 'progress rate' metric for analytical agent evaluation, distinguishing it from pass/fail benchmarks; results correlate with reasoning/coding ability.

[paper](https://arxiv.org/abs/2401.13178) · [code](https://github.com/hkust-nlp/AgentBoard) · [leaderboard](https://hkust-nlp.github.io/agentboard/static/leaderboard.html)

### NATURAL PLAN `T2`
Solve natural-language planning problems in Trip Planning, Meeting Planning, and Calendar Scheduling, given tool outputs (Flights/Maps/Calendar) as context, without needing a live tool-use environment. · **3 task families (Trip, Meeting, Calendar planning) tasks**

> From Google DeepMind; isolates pure planning ability and shows sharp degradation as constraints scale (all models <5% at 10 cities in Trip Planning). Frequently used to probe long-horizon constraint-satisfaction planning in frontier models.

[paper](https://arxiv.org/abs/2406.04520) · [code](https://github.com/google-deepmind/natural-plan)

---

## Multi-Agent

*Collaboration, competition, and social/strategic interaction between agents.*

### SOTOPIA `T1`
Two LLM agents role-play assigned characters with private, sometimes-conflicting social goals across 90 scenarios (negotiation, collaboration, competition) and are scored on goal completion and relationship maintenance via multi-turn interactive social simulation. · **90 social scenarios tasks**

> ICLR 2024 spotlight; the de-facto standard for social/interactive multi-agent intelligence, widely cited and extended (SOTOPIA-pi, SOTOPIA-RL). SOTOPIA-Eval defines 7 social dimensions (BEL, REL, KNO, SEC, SOC, FIN, GOAL).

[paper](https://arxiv.org/abs/2310.11667) · [code](https://github.com/sotopia-lab/sotopia) · [leaderboard](https://huggingface.co/datasets/cmu-lti/sotopia)

### CICERO / Diplomacy evaluation `T3`
An agent must play full-press Diplomacy: simultaneously negotiate, persuade, form and break alliances via free-form natural-language dialogue with six other players while executing strategic moves, evaluated by score and rank against human players in online games. · **1 game (7 players) tasks**

> Meta AI's landmark result: CICERO reached the top 10% of human Diplomacy players, combining a language model with strategic planning/RL. The canonical benchmark for combined negotiation + strategic multi-agent play; recent 'Democratizing Diplomacy' (arXiv:2508.07485) turns it into a reusable harness for any LLM.

[paper](https://arxiv.org/abs/2203.06647) · [code](https://github.com/facebookresearch/diplomacy_cicero)

### GAMA-Bench `T3`
LLMs act as players in eight classical multi-agent game-theory games (across cooperation, betrayal, and sequential settings) under a dynamic scoring scheme that quantitatively measures their decision-making robustness, generalizability, and strategy in multi-agent environments. · **8 game-theory games tasks**

> Game-theory-grounded benchmark for multi-agent decision-making (e.g. public goods, guessing games, auctions); from CUHK-ARISE, frequently cited for evaluating LLM rationality in N-agent settings.

[paper](https://arxiv.org/abs/2403.11807) · [code](https://github.com/CUHK-ARISE/GAMABench)

### MultiAgentBench (MARBLE) `T3`
LLM agents must coordinate (and in some tasks compete) across eight tasks spanning research, software, gaming (Werewolf, Minecraft), database and web scenarios under different coordination topologies (star/chain/tree/graph), scored on milestone-based task and collaboration/competition KPIs. · **8 tasks / scenarios tasks**

> ACL 2025 Main. One of the most comprehensive purpose-built benchmarks for measuring both collaboration AND competition quality (not just task success) across coordination protocols; from UIUC's ulab.

[paper](https://arxiv.org/abs/2503.01935) · [code](https://github.com/MultiagentBench/MARBLE)

### Werewolf Arena `T3`
Eight LLM players (Seer, Doctor, 2 Werewolves, 4 Villagers) compete in the Werewolf social-deduction game using a bidding-based dynamic turn-taking system, testing deception, deduction, and persuasion in an arena-style tournament between models. · **1 game (8 roles) tasks**

> From Google Research; a prominent case study in evaluating LLMs via social deduction, introducing the bidding turn-taking mechanism and arena tournament format between Gemini and GPT models.

[paper](https://arxiv.org/abs/2407.13943) · [code](https://github.com/google/werewolf_arena)

### Collab-Overcooked `T3`
Two LLM agents must cooperate in an extended Overcooked-AI kitchen environment, communicating in natural language to complete 30 open-ended cooking tasks, scored with process-oriented metrics that probe fine-grained collaboration (not just final success). · **30 open-ended tasks tasks**

> EMNLP 2025 Main; notable for process-oriented collaboration metrics that diagnose how (not just whether) agents coordinate, on the well-known Overcooked cooperation testbed.

[paper](https://arxiv.org/abs/2502.20073) · [code](https://github.com/YusaeMeow/Collab-Overcooked)

---

## Science & Research

*Data analysis, ML engineering, and autonomous scientific discovery.*

### MLE-bench `T1`
Given a real Kaggle competition (dataset + task), the agent must run the full ML engineering pipeline — data prep, model training, tuning — and produce a valid submission scored against human leaderboards. · **75 tasks**

> OpenAI (ICLR 2025 Oral); the standard ML-engineering agent benchmark, used in OpenAI and other model cards. o1-preview+AIDE reached Kaggle-bronze level on 16.9% of competitions.

[paper](https://arxiv.org/abs/2410.07095) · [code](https://github.com/openai/mle-bench)

### PaperBench `T1`
Given an ICML 2024 paper, the agent must replicate it from scratch — understand the contributions, build the codebase, and run experiments to reproduce its empirical results. · **20 papers (8,316 gradable sub-tasks) tasks**

> OpenAI benchmark (ICML 2025) with author-co-designed rubrics; used in OpenAI model evaluations. Best agent (Claude 3.5 Sonnet) scored 21% vs 41% for PhD-level humans in 48h.

[paper](https://arxiv.org/abs/2504.01848) · [code](https://github.com/openai/frontier-evals)

### SciCode `T1`
Given a real scientific research problem decomposed into subproblems, the agent must synthesize code that recalls domain knowledge, reasons, and passes scientist-written gold test cases. · **80 problems (338 subproblems) tasks**

> Scientist-curated across physics, math, materials, biology, chemistry. Extremely hard (best model ~4.6% fully solved); used in AstaBench and the Holistic Agent Leaderboard.

[paper](https://arxiv.org/abs/2407.13168) · [code](https://github.com/scicode-bench/SciCode) · [leaderboard](https://scicode-bench.github.io/)

### DiscoveryBench `T2`
Given one or more datasets and a discovery goal, the agent must derive a specific, supported hypothesis by running the full multi-step data-driven discovery workflow. · **264 real + 903 synthetic tasks**

> From Allen Institute for AI; first benchmark to formalize multi-step data-driven discovery across 6 domains derived from published papers. Best system scores ~25%.

[paper](https://arxiv.org/abs/2407.01725) · [code](https://github.com/allenai/discoverybench)

### ScienceAgentBench `T2`
Given a real scientific data-analysis task, the agent must write a self-contained Python program that produces the correct result across bioinformatics, computational chemistry, GIS, and neuroscience. · **102 tasks**

> ICLR 2025; 102 tasks extracted from 44 peer-reviewed papers, validated by 9 domain experts. Widely cited reference benchmark for data-driven scientific discovery; best agents solve only ~32%.

[paper](https://arxiv.org/abs/2410.05080) · [code](https://github.com/OSU-NLP-Group/ScienceAgentBench) · [leaderboard](https://osu-nlp-group.github.io/ScienceAgentBench/)

### BixBench `T2`
Given heterogeneous real biological datasets and an open-ended research question, the agent must perform multi-step computational analysis in a Jupyter environment and interpret the results. · **53 scenarios (296 questions) tasks**

> FutureHouse + ScienceMachine; derived from 60 real published bioinformatics notebooks. Frontier models (GPT-4o, Claude 3.5 Sonnet) reach only ~17% in open-answer mode.

[paper](https://arxiv.org/abs/2503.00096) · [code](https://github.com/Future-House/BixBench)

### CORE-Bench `T2`
Given a published paper's code and data in a Docker environment, the agent must computationally reproduce the reported results and answer questions about them. · **270 tasks**

> Princeton; 270 tasks from 90 papers across CS, social science, and medicine at 3 difficulty levels. Hosted on the Holistic Agent Leaderboard (HAL); a standard reproducibility eval.

[paper](https://arxiv.org/abs/2409.11363) · [code](https://github.com/siegelz/core-bench) · [leaderboard](https://hal.cs.princeton.edu/corebench_hard)

### RE-Bench `T3`
Given open-ended ML research-engineering environments (e.g. fit a scaling law, optimize a GPU kernel), the agent must maximize a measurable score, benchmarked head-to-head against human experts. · **7 tasks**

> METR; directly compares frontier agents against 61 human experts on AI R&D automation. Central to frontier-AI safety/capability evaluations; agents beat humans at 2h but lag at longer budgets.

[paper](https://arxiv.org/abs/2411.15114) · [code](https://github.com/METR/ai-rd-tasks)

### AstaBench `T3`
The agent must complete entire scientific research workflows — literature search, code execution, data analysis, and end-to-end discovery — within a standardized, reproducible research environment. · **2400+ across 11 benchmarks tasks**

> Allen Institute for AI (2025); a holistic suite whose leaderboard is the first to control for tools used and inference cost. Evaluated 57 agents; AI still far from solving research assistance.

[paper](https://arxiv.org/abs/2510.21652) · [code](https://github.com/allenai/asta-bench) · [leaderboard](https://allenai.org/asta/bench)

---

## Safety, Security & Robustness

*Prompt injection, harmful-tool refusal, and adversarial robustness.*

### AgentDojo `T1`
In realistic environments (email client, e-banking, travel booking) the agent must complete legitimate user tasks while resisting prompt-injection instructions hidden in tool/data outputs that try to hijack its behavior. · **97 realistic tasks, 629 security test cases tasks**

> One of the most influential prompt-injection agent benchmarks; NeurIPS 2024 Datasets & Benchmarks; maintains a public leaderboard and is the standard testbed for injection attacks/defenses (CaMeL, StruQ, Meta SecAlign all report on it).

[paper](https://arxiv.org/abs/2406.13352) · [code](https://github.com/ethz-spylab/agentdojo) · [leaderboard](https://agentdojo.spylab.ai)

### AgentDojo `T1`
A dynamic environment of 97 realistic tool-using tasks plus 629 prompt-injection security test cases, where an attacker plants malicious instructions in tool outputs and the agent must complete the task without being hijacked. · **97 tasks + 629 injection cases tasks**

> NeurIPS 2024 Datasets & Benchmarks; the reference prompt-injection / tool-use security benchmark, used as the standard testbed for injection attacks and defenses (CaMeL, StruQ, Meta SecAlign all report on it).

[paper](https://arxiv.org/abs/2406.13352) · [code](https://github.com/ethz-spylab/agentdojo) · [leaderboard](https://agentdojo.spylab.ai/)

### AgentHarm `T1`
Given an explicitly malicious multi-step request (e.g. fraud, cybercrime, harassment), the tool-using agent must either refuse or, if jailbroken, the benchmark measures whether it still completes the harmful task end-to-end. · **110 base behaviors (440 with augmentations) across 11 harm categories, 104 tools tasks**

> De facto standard for agent harmfulness/jailbreak robustness; built by the UK AI Safety Institute, integrated into Inspect Evals, and widely cited in model safety cards and red-teaming work.

[paper](https://arxiv.org/abs/2410.09024) · [code](https://github.com/UKGovernmentBEIS/inspect_evals) · [leaderboard](https://huggingface.co/datasets/ai-safety-institute/AgentHarm)

### InjecAgent `T1`
The tool-integrated agent processes content returned by tools that contains injected attacker instructions, and is scored on whether it executes attacks causing direct harm to the user or exfiltration of private data. · **1,054 test cases, 17 user tools, 62 attacker tools tasks**

> Early and widely-cited indirect-prompt-injection benchmark for agents (ACL 2024 Findings); commonly used as a baseline alongside AgentDojo.

[paper](https://arxiv.org/abs/2403.02691) · [code](https://github.com/uiuc-kang-lab/InjecAgent)

### AgentPoison `T2`
Red-teams a RAG/memory-augmented LLM agent by poisoning its knowledge base or memory with a tiny number of crafted entries, then measures how reliably the backdoor triggers malicious actions. · **<0.1% poison rate, 80%+ attack success tasks**

> NeurIPS 2024; Dawn Song (UC Berkeley) is a direct author. The canonical memory/knowledge-base poisoning attack benchmark for agentic RAG systems.

[paper](https://arxiv.org/abs/2407.12784) · [code](https://github.com/AI-secure/AgentPoison)

### R-Judge `T2`
Given a multi-turn agent interaction record, the model must judge whether the agent's behavior was unsafe and identify the safety risk, testing risk awareness rather than content harmlessness. · **569 multi-turn records, 27 risk scenarios, 10 risk types tasks**

> Standard benchmark for agent safety-risk awareness / LLM-as-safety-judge (EMNLP 2024 Findings); frequently used to evaluate guardrail and judge models.

[paper](https://arxiv.org/abs/2401.10019) · [code](https://github.com/Lordog/R-Judge)

### RedCode `T2`
A code agent is given prompts to execute or generate code, and is scored on whether it recognizes and refuses risky operations (RedCode-Exec) and whether it declines to produce harmful software (RedCode-Gen). · **4,050 execution instances + 160 generation prompts (~4,000+ total) tasks**

> Leading safety benchmark for code/coding agents (NeurIPS 2024 Datasets & Benchmarks); covers 25 vulnerability types across 8 domains with real Docker execution.

[paper](https://arxiv.org/abs/2411.07781) · [code](https://github.com/AI-secure/RedCode) · [leaderboard](https://redcode-agent.github.io/)

### OS-Harm `T2`
Measures the safety of computer-use (GUI) agents across 150 tasks spanning deliberate user misuse, prompt-injection attacks, and unprompted model misbehavior, judged by an automated safety evaluator. · **150 tasks**

> NeurIPS 2025 Spotlight; the first benchmark dedicated to computer-use agent safety (built on OSWorld), covering misuse, injection, and misbehavior in one suite.

[paper](https://arxiv.org/abs/2506.14866) · [code](https://github.com/tml-epfl/os-harm)

### Agent Security Bench (ASB) `T3`
Across 10 agent scenarios (e-commerce, finance, autonomous driving, etc.) the agent is subjected to formalized attacks (prompt injection, memory poisoning, Plan-of-Thought backdoor) and paired defenses, scored by attack success rate. · **~90,000 test cases; 10 scenarios, 400+ tools, 27 attack/defense methods tasks**

> Most comprehensive single framework formalizing agent attacks AND defenses; ~90,000 test cases; widely cited in agent-security surveys for covering injection, memory, and backdoor vectors together.

[paper](https://arxiv.org/abs/2410.02644) · [code](https://github.com/agiresearch/ASB)

### Agent-SafetyBench `T3`
Across hundreds of interactive tool environments the agent faces tasks spanning 8 safety-risk categories, and is scored on whether its behavior avoids unsafe outcomes across 10 common failure modes. · **2,000 test cases across 349 environments tasks**

> Broad, widely-cited agent safety benchmark from THU-CoAI; notable finding that none of 16 popular agents scored above 60% safety, attributing failures to weak robustness and risk awareness.

[paper](https://arxiv.org/abs/2412.14470) · [code](https://github.com/thu-coai/Agent-SafetyBench)

### OpenAgentSafety `T3`
Evaluates agent safety in realistic multi-tool environments across 350+ executable tasks and 8 risk categories, using real tools (browser, shell, file system) rather than simulated ones. · **350+ tasks**

> ICLR 2026; one of the broadest executable agent-safety benchmarks grounded in real tool execution rather than emulation.

[paper](https://arxiv.org/abs/2507.06134) · [code](https://github.com/sani903/OpenAgentSafety)

### SafeArena `T3`
A web agent operating in self-hosted WebArena sites is given matched safe and harmful tasks (misinformation, illegal activity, harassment, cybercrime, social bias) and is scored on its compliance with the harmful requests. · **500 tasks (250 safe + 250 harmful) across 5 harm categories tasks**

> First benchmark focused on deliberate misuse of autonomous web agents (McGill-NLP, 2025); has a public leaderboard and found GPT-4o completed ~35% of harmful tasks.

[paper](https://arxiv.org/abs/2503.04957) · [code](https://github.com/McGill-NLP/safearena) · [leaderboard](https://safearena.github.io/)

---

## Cybersecurity (Offensive)

*Finding and exploiting real vulnerabilities, CTFs, and bug bounties.*

### CyberGym `T1`
Tasks agents with finding and exploiting real software vulnerabilities across 1,500+ C/C++ targets drawn from open-source projects, scored by producing a working proof-of-concept exploit. · **1,507 real vulnerabilities tasks**

> UC Berkeley (sunblaze-ucb, Dawn Song group); a large-scale real-vulnerability exploitation benchmark that surfaced dozens of zero-days. One of the most rigorous offensive-security agent evals.

[paper](https://arxiv.org/abs/2506.02548) · [code](https://github.com/sunblaze-ucb/cybergym) · [leaderboard](https://www.cybergym.io/)

### CyBench `T1`
Evaluates agents on 40 professional-level Capture-the-Flag (CTF) cybersecurity tasks from real competitions, requiring multi-step exploitation in a sandboxed environment. · **40 CTF tasks tasks**

> A widely-cited CTF agent benchmark used to measure offensive cyber capability of frontier models (GPT-4o, Claude 3.5, etc.); a reference point in cyber-risk evaluations.

[paper](https://arxiv.org/abs/2408.08926) · [code](https://github.com/andyzorigin/cybench)

### CVE-Bench `T2`
Tests whether an agent can exploit real-world web-application vulnerabilities reproduced from actual CVEs, in isolated containerized environments, scored by successful exploitation. · **40 CVEs tasks**

> ICML 2025; UIUC. The first benchmark built on real CVEs for web-app exploitation, used by the US AI Safety Institute for capability evaluation.

[paper](https://arxiv.org/abs/2503.17332) · [code](https://github.com/uiuc-kang-lab/cve-bench)

### BountyBench `T2`
Grounds agent cyber capability in real money: 25 real systems and 40 real bug bounties ($10–30K payouts), with Detect / Exploit / Patch task formulations. · **25 systems, 40 bounties tasks**

> NeurIPS 2025; the first benchmark to tie agent cyber performance to real bug-bounty economics across the full detect-exploit-patch lifecycle.

[paper](https://arxiv.org/abs/2505.15216) · [code](https://github.com/cybench/BountyBench) · [leaderboard](https://bountybench.github.io/)

---

## General & Real-World Work

*Cross-domain office/company tasks that mirror real knowledge work.*

### AgentBench `T1`
Evaluate an LLM as an agent across 8 distinct interactive environments (OS, database, knowledge graph, card game, web shopping/browsing, etc.) in multi-turn open-ended settings. · **8 environments tasks**

> ICLR 2024; one of the earliest and most-cited multi-environment LLM-as-agent benchmarks (Tsinghua/THUDM), evaluated 27 LLMs and surfaced the closed-vs-open-source agent capability gap.

[paper](https://arxiv.org/abs/2308.03688) · [code](https://github.com/THUDM/AgentBench)

### OSWorld `T1`
Drive a real Ubuntu/Windows/macOS computer via screenshots and GUI/CLI actions to complete 369 open-ended desktop and web tasks spanning multiple applications, evaluated by execution scripts. · **369 tasks**

> NeurIPS 2024; the standard real-computer-use benchmark (XLang Lab) referenced in Anthropic/OpenAI computer-use model cards. Humans solve >72% vs ~12% for early best models, with rapid leaderboard progress since.

[paper](https://arxiv.org/abs/2404.07972) · [code](https://github.com/xlang-ai/OSWorld) · [leaderboard](https://os-world.github.io/)

### Terminal-Bench `T1`
Complete hard, realistic end-to-end command-line tasks in a sandboxed terminal — compiling code, configuring legacy systems, training models, security and data-science workflows — verified by execution. · **89 (Core v0.1.1) tasks**

> Stanford x Laude Institute (ICLR 2026); a heavily-used agentic-terminal leaderboard cited in frontier model cards, with active 1.0/2.0/2.1 and Hard versions tracked on multiple aggregator sites.

[paper](https://arxiv.org/abs/2601.11868) · [code](https://github.com/laude-institute/terminal-bench) · [leaderboard](https://www.tbench.ai/leaderboard)

### TheAgentCompany `T1`
Act as a digital worker inside a self-hosted simulated software company, browsing internal sites, writing code, running programs, and messaging simulated coworkers to complete consequential workplace tasks. · **175 tasks**

> Influential real-workplace benchmark (CMU et al.) with a self-contained GitLab/Plane/RocketChat/ownCloud environment; best agents complete only ~30% of full tasks. Public leaderboard and submission process.

[paper](https://arxiv.org/abs/2412.14161) · [code](https://github.com/TheAgentCompany/TheAgentCompany) · [leaderboard](https://the-agent-company.com/)

### GAIA `T1`
Answer 466 human-authored real-world assistant questions that require multi-step reasoning, web browsing, multimodality, and tool use, each with a single verifiable short answer. · **466 tasks**

> The canonical general-AI-assistant benchmark (FAIR/Meta, HuggingFace, AutoGPT). Humans score 92% vs ~15% for GPT-4+plugins at launch; widely cited and reported in model cards and agent frameworks.

[paper](https://arxiv.org/abs/2311.12983) · [code](https://github.com/aymeric-roucher/GAIA) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### Agents' Last Exam (ALE) `T2`
Asks agents to perform economically valuable, expert-sourced work across 55 occupations and 1,500+ real tasks, scoring whether outputs meet professional standards. · **1,500+ across 55 occupations tasks**

> Berkeley RDI flagship (directed by Dawn Song); an economically-grounded successor in spirit to GAIA, mapping agent capability to real industry work.

[paper](https://arxiv.org/abs/2606.05405) · [code](https://github.com/rdi-berkeley/agents-last-exam) · [leaderboard](https://agents-last-exam.org/)

### AssistantBench `T2`
Solve 214 realistic, time-consuming open-web tasks (e.g. monitoring real-estate markets, finding nearby businesses) that require navigating live websites, with automatically verifiable answers. · **214 tasks**

> Allen Institute/Bar-Ilan/Penn benchmark for realistic web assistance; exposed that no model exceeded ~25 accuracy and SOTA web agents scored near zero, motivating the SeePlanAct agent.

[paper](https://arxiv.org/abs/2407.15711) · [code](https://github.com/oriyor/assistantbench) · [leaderboard](https://assistantbench.github.io/)

### Gaia2 (Meta Agents Research Environments / ARE) `T3`
Operate across 800 scenarios in 10 simulated 'universes' with 11 apps, handling asynchronous, evolving environments under time constraints, ambiguity, noise, and multi-agent collaboration. · **800 tasks**

> Meta's 2025 successor to GAIA built on the ARE platform; introduces dynamic/asynchronous environments measuring execution, search, adaptability, temporal reasoning, ambiguity, and multi-agent capabilities. Actively maintained leaderboard.

[paper](https://arxiv.org/abs/2509.17158) · [code](https://github.com/facebookresearch/meta-agents-research-environments) · [leaderboard](https://huggingface.co/spaces/meta-agents-research-environments/leaderboard)

### CRMArena / CRMArena-Pro `T3`
Perform expert-validated professional CRM tasks (service, sales, configure-price-quote) over a populated Salesforce org with tens of thousands of records, across single- and multi-turn interactions. · **19 task types (CRMArena-Pro) tasks**

> Salesforce AI Research's enterprise-grounded benchmark; widely cited finding that top agents reach only ~58% single-turn and drop to ~35% multi-turn success. CRMArena (arXiv:2411.02305) is the original; Pro is the expanded B2B/B2C version.

[paper](https://arxiv.org/abs/2505.18878) · [code](https://github.com/SalesforceAIResearch/CRMArena) · [leaderboard](https://huggingface.co/spaces/Salesforce/CRMArena-Leaderboard)

---

## Contributing

Add a benchmark if it is real, used, and verifiable.

- Include the paper and/or code URL. Verify both are live before submitting.
- One concrete sentence: what the agent actually has to do.
- Put it in the dimension it most belongs to, and suggest a tier. One entry per PR.

```markdown
### Benchmark Name `T2`
One sentence on what the agent must do. · **N tasks**

[paper](url) · [code](url) · [leaderboard](url)
```

---

*Maintained as part of [first-tree](https://github.com/unispark-inc/first-tree?ref=awesome-ai-agent-benchmarks) — shared context infrastructure for agent teams.*