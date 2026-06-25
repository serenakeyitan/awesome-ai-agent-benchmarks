# Awesome AI Agent Benchmarks

A curated, dimension-organized index of **52 benchmarks** for evaluating LLM-based AI agents — with **how to actually run each one**.

Evaluating AI agents is hard, and *running* the benchmarks is half the battle: each one has its own setup, and you bring your own agent. This list organizes the benchmarks that matter across **10 capability dimensions**, ranks them by influence tier, and — for every entry — tells you the setup, a run command, and how heavy it is to stand up. Start with a unified harness, pick a 🟢 light benchmark, and go.

> Curated by the [first-tree](https://github.com/unispark-inc/first-tree?ref=awesome-ai-agent-benchmarks) team.

---

## Contents

- [How to run these benchmarks](#how-to-run-these-benchmarks)
- [The index (all benchmarks, by influence tier)](#the-index)
- [Coding & Software Engineering](#coding--software-engineering) (8)
- [Web Browsing & Navigation](#web-browsing--navigation) (7)
- [Computer Use (GUI / OS)](#computer-use-gui--os) (4)
- [Tool Use & Function Calling](#tool-use--function-calling) (5)
- [Reasoning & Planning](#reasoning--planning) (4)
- [Multi-Agent](#multi-agent) (4)
- [Science & Research](#science--research) (4)
- [Safety, Security & Robustness](#safety-security--robustness) (6)
- [Cybersecurity (Offensive)](#cybersecurity-offensive) (4)
- [General & Real-World Work](#general--real-world-work) (6)

---

## How to run these benchmarks

The honest version:

- **You bring the agent.** Benchmarks supply tasks and scoring; you plug in your model/agent (via an API key or a local model).
- **Setup is the real cost.** A 🟢 light one is `pip install` + an API key. A 🔴 heavy one needs Docker, a VM, or a self-hosted website.
- **There is no one-click-runs-all.** But unified harnesses below wrap many benchmarks behind one interface — use those first.

### Start with a unified harness

These run *multiple* benchmarks through one standardized interface, so you write your agent once.

| Harness | What it gives you | Runs | Install |
|---|---|---|---|
| [Inspect AI](https://github.com/UKGovernmentBEIS/inspect_ai) | UK AISI's Python framework for reproducible LLM and agent evaluations  | Agent tool-use, multi-turn workflows, OWASP Top 10 for  | `pip install inspect-ai` |
| [lm-evaluation-harness (EleutherAI)](https://github.com/EleutherAI/lm-evaluation-harness) | Unified framework for few-shot evaluation of language models across 60 | MMLU, GSM8K, MBPP, HellaSwag, TinyBenchmarks, long-cont | `pip install lm-eval` |
| [OpenHands](https://github.com/All-Hands-AI/OpenHands) | Evaluation harness for OpenHands V1 agents with remote container runti | SWE-Bench (real-world software engineering), SWT-Bench  | `git clone + pip install -e` |
| [BrowserGym](https://github.com/ServiceNow/BrowserGym) | Unified gym-like environment for web agent research that integrates 7  | MiniWoB, WebArena, VisualWebArena, WorkArena, Assistant | `pip install browsergym` |
| [HAL (Holistic Agent Leaderboard)](https://github.com/princeton-pli/hal-harness) | Princeton's standardized, cost-aware evaluation harness that unifies 1 | SWE-bench, USACO, CORE-bench, Cybench, AgentHarm, 7+ ot | `git clone + pip install -e` |
| [PromptFoo](https://github.com/promptfoo/promptfoo) | CLI-first testing suite for evaluating prompts, agents, and RAGs with  | LangGraph agents, OSWorld+Inspect, coding agents, HLE B | `pip install promptfoo` |

### Where to start, by setup cost

Difficulty below means **setup/resource burden, not task hardness** (GAIA is 🟢 to run but hard to score well on).

- **🟢 light** — `pip install` + an API key. Runs on your laptop in minutes. Best first benchmarks: **τ-bench**, **BFCL**, **AgentHarm**, **GAIA**, **SOTOPIA**, **SciCode**.
- **🟡 medium** — needs **Docker**. Containerized task execution; budget some disk and an hour+. e.g. **AgentDojo**, **CyBench**, **AndroidWorld**.
- **🔴 heavy** — needs a **VM or self-hosted environment** (full websites, desktop VMs, 100GB+ disk). e.g. **SWE-bench**, **WebArena**, **OSWorld**, **CyberGym**.

Every entry below shows its **setup**, a **difficulty badge**, and (where documented) a **minimal run command** — so you can tell at a glance what it takes before you commit.

---

## The index

Every benchmark, ranked by **influence tier**, then by GitHub stars. Tier reflects real-world adoption (Tier 1 = reported in frontier model cards). The **Run** column shows setup difficulty. (Stars `*` belong to a parent framework, not the benchmark alone.)

### Tier 1 — frontier model-card standard  (27)

| Benchmark | Dimension | What it tests | Run | Stars |
|---|---|---|---|---:|
| [BFCL (Berkeley Function-Calling Leaderboard)](https://github.com/ShishirPatil/gorilla) | Tool Use | Given a natural-language request and a set of function/API… | 🟢 light | 12.9k* |
| [SWE-bench](https://github.com/SWE-bench/SWE-bench) | Coding | Given a real GitHub issue and the full repository, the age… | 🔴 heavy | 5.2k |
| [SWE-bench Verified](https://github.com/SWE-bench/SWE-bench) | Coding | Same task as SWE-bench (resolve a real GitHub issue via a… | 🔴 heavy | 5.2k |
| [SWE-bench Multimodal](https://github.com/SWE-bench/SWE-bench) | Coding | Resolve real GitHub issues in user-facing JavaScript repos… | 🔴 heavy | 5.2k |
| [BrowseComp](https://github.com/openai/simple-evals) | Web | Answer 'inverted' questions that require persistent, creat… | 🟢 light | 4.5k* |
| [AgentBench](https://github.com/THUDM/AgentBench) | Reasoning | Operate as an autonomous agent across 8 distinct interacti… | 🟡 medium | 3.5k |
| [OSWorld](https://github.com/xlang-ai/OSWorld) | Computer Use | Execute 369 open-ended real-computer tasks (file ops, desk… | 🔴 heavy | 3k |
| [Terminal-Bench](https://github.com/laude-institute/terminal-bench) | Coding | Autonomously complete hard, end-to-end tasks in a real com… | 🔴 heavy | 2.4k |
| [MLE-bench](https://github.com/openai/mle-bench) | Science | Given a real Kaggle competition (dataset + task), the agen… | 🔴 heavy | 1.6k |
| [WebArena](https://github.com/web-arena-x/webarena) | Web | Complete high-level natural-language tasks (e-commerce, fo… | 🔴 heavy | 1.5k |
| [SWE-Lancer](https://github.com/openai/SWELancer-Benchmark) | Coding | Complete real paid Upwork freelance software-engineering t… | 🟡 medium | 1.4k |
| [tau-bench (τ-bench)](https://github.com/sierra-research/tau-bench) | Tool Use | The agent plays a customer-service rep that must converse… | 🟢 light | 1.3k |
| [PaperBench](https://github.com/openai/frontier-evals) | Science | Given an ICML 2024 paper, the agent must replicate it from… | 🟡 medium | 1.2k |
| [WebVoyager](https://github.com/MinorJerry/WebVoyager) | Web | Complete end-to-end tasks on 15 live, high-traffic real we… | 🟡 medium | 1.1k |
| [Mind2Web](https://github.com/OSU-NLP-Group/Mind2Web) | Web | Predict the correct action sequence (element selection + o… | 🟢 light | 1k |
| [LiveCodeBench](https://github.com/LiveCodeBench/LiveCodeBench) | Coding | Solve competitive-programming problems continuously scrape… | 🟡 medium | 888 |
| [AndroidWorld](https://github.com/google-research/android_world) | Computer Use | Complete 116 programmatic tasks across 20 real Android app… | 🟡 medium | 800 |
| [TheAgentCompany](https://github.com/TheAgentCompany/TheAgentCompany) | General | Act as a digital worker inside a self-hosted simulated sof… | 🟡 medium | 727 |
| [AgentDojo](https://github.com/ethz-spylab/agentdojo) | Safety | In realistic environments (email client, e-banking, travel… | 🟢 light | 630 |
| [AgentHarm](https://github.com/UKGovernmentBEIS/inspect_evals) | Safety | Given an explicitly malicious multi-step request (e.g. fra… | 🟢 light | 551 |
| [VisualWebArena](https://github.com/web-arena-x/visualwebarena) | Web | Solve realistic visually-grounded web tasks (image-text in… | 🔴 heavy | 481 |
| [PlanBench](https://github.com/karthikv792/LLMs-Planning) | Reasoning | Generate and reason about plans in classical IPC planning… | 🔴 heavy | 466 |
| [CyberGym](https://github.com/sunblaze-ucb/cybergym) | Cybersecurity | Tasks agents with finding and exploiting real software vul… | 🔴 heavy | 431 |
| [SOTOPIA](https://github.com/sotopia-lab/sotopia) | Multi-Agent | Two LLM agents role-play assigned characters with private,… | 🟢 light | 312 |
| [CyBench](https://github.com/andyzorigin/cybench) | Cybersecurity | Evaluates agents on 40 professional-level Capture-the-Flag… | 🟢 light | 266 |
| [SciCode](https://github.com/scicode-bench/SciCode) | Science | Given a real scientific research problem decomposed into s… | 🟢 light | 208 |
| [GAIA](https://arxiv.org/abs/2311.12983) | Web | Answer real-world assistant questions that require multi-s… | 🟢 light | — |

### Tier 2 — widely used  (11)

| Benchmark | Dimension | What it tests | Run | Stars |
|---|---|---|---|---:|
| [ToolBench (ToolLLM)](https://github.com/OpenBMB/ToolBench) | Tool Use | Given user instructions, the agent must select and chain c… | 🟡 medium | 5.7k* |
| [Agents' Last Exam (ALE)](https://github.com/rdi-berkeley/agents-last-exam) | General | Asks agents to perform economically valuable, expert-sourc… | 🔴 heavy | 721 |
| [TravelPlanner](https://github.com/OSU-NLP-Group/TravelPlanner) | Reasoning | Act as a travel-planning agent that queries a sandbox of ~… | 🟡 medium | 523 |
| [BigCodeBench](https://github.com/bigcode-project/bigcodebench) | Coding | Write Python functions that correctly compose multiple lib… | 🟢 light | 509 |
| [Multi-SWE-bench](https://github.com/multi-swe-bench/multi-swe-bench) | Coding | Resolve real GitHub issues via patches that pass hidden te… | 🔴 heavy | 341 |
| [CVE-Bench](https://github.com/uiuc-kang-lab/cve-bench) | Cybersecurity | Tests whether an agent can exploit real-world web-applicat… | 🟡 medium | 240 |
| [AgentPoison](https://github.com/AI-secure/AgentPoison) | Safety | Red-teams a RAG/memory-augmented LLM agent by poisoning it… | 🔴 heavy | 222 |
| [Online-Mind2Web](https://github.com/OSU-NLP-Group/Online-Mind2Web) | Web | Execute 300 realistic tasks on 136 live websites in an onl… | 🟡 medium | 182 |
| [ScienceAgentBench](https://github.com/OSU-NLP-Group/ScienceAgentBench) | Science | Given a real scientific data-analysis task, the agent must… | 🟡 medium | 141 |
| [OS-Harm](https://github.com/tml-epfl/os-harm) | Safety | Measures the safety of computer-use (GUI) agents across 15… | 🔴 heavy | 67 |
| [BountyBench](https://github.com/cybench/BountyBench) | Cybersecurity | Grounds agent cyber capability in real money: 25 real syst… | 🔴 heavy | 9 |

### Tier 3 — emerging / niche  (8)

| Benchmark | Dimension | What it tests | Run | Stars |
|---|---|---|---|---:|
| [tau2-bench (τ²-bench)](https://github.com/sierra-research/tau2-bench) | Tool Use | Extends tau-bench to dual-control settings where both the… | 🟡 medium | 1.4k |
| [WindowsAgentArena (WAA)](https://github.com/microsoft/WindowsAgentArena) | Computer Use | Complete 154 multi-step Windows-OS tasks across real apps… | 🔴 heavy | 874 |
| [ScreenSpot-Pro](https://github.com/likaixin2000/ScreenSpot-Pro-GUI-Grounding) | Computer Use | Locate tiny, cluttered UI targets from instructions on ult… | 🟢 light | 378 |
| [Agent Security Bench (ASB)](https://github.com/agiresearch/ASB) | Safety | Across 10 agent scenarios (e-commerce, finance, autonomous… | 🟡 medium | 264 |
| [ToolSandbox](https://github.com/apple/ToolSandbox) | Tool Use | A stateful, conversational benchmark with an on-policy LLM… | 🟢 light | 261 |
| [GAMA-Bench](https://github.com/CUHK-ARISE/GAMABench) | Multi-Agent | LLMs act as players in eight classical multi-agent game-th… | 🟢 light | 97 |
| [MultiAgentBench (MARBLE)](https://github.com/MultiagentBench/MARBLE) | Multi-Agent | LLM agents must coordinate (and in some tasks compete) acr… | 🟢 light | 51 |
| [Collab-Overcooked](https://github.com/YusaeMeow/Collab-Overcooked) | Multi-Agent | Two LLM agents must cooperate in an extended Overcooked-AI… | 🟢 light | 35 |

<sub>`*` = star count is for the parent framework, not the benchmark alone. Run difficulty = setup/resource burden, not task hardness.</sub>

---

## Coding & Software Engineering

*Resolving real issues, writing code, building libraries, working in the terminal.*

### SWE-bench `T1` 🔴
Given a real GitHub issue and the full repository, the agent must produce a code patch (diff) that resolves the issue and passes the repo's hidden test suite. · **2294 tasks**

> The foundational real-world software-engineering benchmark (ICLR 2024, Princeton). 2,294 tasks across 12 Python repos. Cited everywhere and the basis for most agentic coding evals and model cards.

**Run:** 🔴 heavy · setup: Docker + pip · ~hours to days (resource-intensive)

```bash
python -m swebench.harness.run_evaluation --predictions_path gold --max_workers 1 --instance_ids sympy__sympy-20590 --run_id validate-gold
```
<sub>⚠️ Requires 120GB free disk, 16GB RAM, 8 CPU cores; Docker Desktop users must increase virtual disk to ~200GB; ARM64 support experimental</sub>

[paper](https://arxiv.org/abs/2310.06770) · [code](https://github.com/SWE-bench/SWE-bench) · [leaderboard](https://www.swebench.com/)

### SWE-bench Verified `T1` 🔴
Same task as SWE-bench (resolve a real GitHub issue via a patch that passes hidden tests), but on a 500-instance human-validated subset where problems are confirmed solvable and tests are correct. · **500 tasks**

> The de facto industry-standard coding-agent metric, built with OpenAI human annotators. Headline number in nearly every frontier-model release (Claude, GPT, Gemini) and the most-watched coding leaderboard.

**Run:** 🔴 heavy · setup: Docker + pip · ~hours to days

```bash
python -m swebench.harness.run_evaluation --dataset_name princeton-nlp/SWE-bench_Lite --predictions_path <predictions> --max_workers <num> --run_id <name>
```
<sub>⚠️ Smaller subset (500 instances) than full SWE-bench; same Docker/resource requirements; use fewer than min(0.75*cpu_count(), 24) workers</sub>

[paper](https://arxiv.org/abs/2310.06770) · [code](https://github.com/SWE-bench/SWE-bench) · [leaderboard](https://www.swebench.com/verified.html)

### SWE-bench Multimodal `T1` 🔴
Resolve real GitHub issues in user-facing JavaScript repos where the problem statement or tests include images (UI bugs, data-viz, mapping), requiring visual reasoning plus code editing. · **619 tasks**

> First benchmark testing coding agents on visual/front-end software domains; 619 tasks from 17 JS repos. Top systems resolve only ~12%, exposing a large gap beyond text-only Python tasks.

**Run:** 🔴 heavy · setup: Docker + pip · ~hours to days

```bash
python -m swebench.harness.run_evaluation --dataset_name princeton-nlp/SWE-bench_Multimodal --predictions_path <predictions> --max_workers <num> --run_id <name>
```
<sub>⚠️ Requires vision capability for JavaScript UI repos; same Docker/disk requirements as core SWE-bench; fewer instances (619) but harder due to visual reasoning</sub>

[paper](https://arxiv.org/abs/2410.03859) · [code](https://github.com/SWE-bench/SWE-bench)

### Terminal-Bench `T1` 🔴
Autonomously complete hard, end-to-end tasks in a real command-line environment (compiling code, training models, configuring servers, sysadmin, security) verified by automated checks. · **89 tasks**

> Stanford / Laude Institute benchmark for terminal/CLI agents; widely adopted across scaffolds (Codex CLI, OpenHands, Aider, Claude Code). v2.0 evaluates 89 tasks with multiple trials and 100+ agents on the leaderboard.

**Run:** 🔴 heavy · setup: Docker + pip + Python 3.x · ~not specified; parallelizable via --n-concurrent

```bash
tb run
```
<sub>⚠️ Distributed as pip package; also available via 'uv tool install terminal-bench'; full command: tb run --agent terminus --model anthropic/claude-3-7-latest --dataset-name terminal-bench-core --dataset-version 0.1.1 --n-concurrent 8</sub>

[code](https://github.com/laude-institute/terminal-bench) · [leaderboard](https://www.tbench.ai/leaderboard)

### SWE-Lancer `T1` 🟡
Complete real paid Upwork freelance software-engineering tasks (bug fixes to feature builds) graded by end-to-end tests, plus managerial tasks choosing between implementation proposals. · **1488 tasks**

> OpenAI benchmark of 1,400+ tasks worth $1M in real payouts; maps model performance to dollar value. The leading economically-grounded real-world SWE benchmark, used in OpenAI model evaluations.

**Run:** 🟡 medium · setup: uv + pip · ~not specified; varies per task

```bash
uv sync && uv run pytest
```
<sub>⚠️ Archived repo merged into openai/preparedness; real freelance tasks with end-to-end tests; each eval has isolated pyproject.toml; run from project/swelancer/ directory</sub>

[paper](https://arxiv.org/abs/2502.12115) · [code](https://github.com/openai/SWELancer-Benchmark)

### LiveCodeBench `T1` 🟡
Solve competitive-programming problems continuously scraped from LeetCode, AtCoder and Codeforces, with code generation plus self-repair, code execution, and test-output prediction. · **1000+ tasks**

> The standard contamination-free code-generation benchmark; problems are date-stamped so models are scored only on problems released after their training cutoff. Widely cited and used in model cards.

**Run:** 🟡 medium · setup: pip + Python 3.11 · ~1-6 hours (varies by model)

```bash
python -m lcb_runner.runner.main --model {model_name} --scenario codegeneration --evaluate
```
<sub>⚠️ Requires Python 3.11 and uv package manager; vLLM needed for GPU inference; time limits can cause <0.5pt variation in metrics; use --not_fast for full eval, lite is default</sub>

[paper](https://arxiv.org/abs/2403.07974) · [code](https://github.com/LiveCodeBench/LiveCodeBench)

### BigCodeBench `T2` 🟢
Write Python functions that correctly compose multiple library/API calls (139 libraries, 7 domains) to satisfy complex natural-language instructions, verified by rich test cases. · **1140 tasks**

> ICLR 2025; the leading benchmark for realistic library-heavy coding (1,140 tasks, 723 function calls). Best LLMs reach ~60% vs 97% human, making it a hard, widely-used signal beyond toy code generation.

**Run:** 🟢 light · setup: pip + optional API keys (E2B/OpenAI/Anthropic/Mistral/Google/HF) · ~4-30 minutes (Gradio: 6-7 min full, 4-5 min hard; E2B: 25-30 min full, 15-20 min hard)

```bash
bigcodebench.evaluate --model meta-llama/Meta-Llama-3.1-8B-Instruct --execution gradio --split complete --subset full --backend vllm
```
<sub>⚠️ Batch size affects results (set to 1 for deterministic); auto-detects base vs chat models; default Gradio endpoint can be slow; requires packaging and ninja for compilation</sub>

[paper](https://arxiv.org/abs/2406.15877) · [code](https://github.com/bigcode-project/bigcodebench) · [leaderboard](https://bigcode-bench.github.io/)

### Multi-SWE-bench `T2` 🔴
Resolve real GitHub issues via patches that pass hidden tests, but across 7 non-Python languages (Java, TypeScript, JavaScript, Go, Rust, C, C++). · **1632 tasks**

> First large multilingual issue-resolving benchmark (ByteDance Seed), 1,632 issues. Increasingly used to show coding agents generalize beyond Python.

**Run:** 🔴 heavy · setup: Docker + pip + HF datasets · ~12-24+ hours

```bash
python -m multi_swe_bench.harness.run_evaluation --config /path/to/config.json
```
<sub>⚠️ Covers 7 non-Python languages; requires dataset from Hugging Face; config file specifies patches in JSONL format; same Docker infrastructure as SWE-bench</sub>

[paper](https://arxiv.org/abs/2504.02605) · [code](https://github.com/multi-swe-bench/multi-swe-bench)

---

## Web Browsing & Navigation

*Driving live or cloned websites: shopping, research, form-filling, multi-step navigation.*

### BrowseComp `T1` 🟢
Answer 'inverted' questions that require persistent, creative web browsing to locate hard-to-find, entangled facts, with short answers that are easy to verify against references. · **1266 tasks**

> OpenAI (2025); the reference benchmark for deep-research / persistent-browsing agents, used in OpenAI Deep Research and frontier-model model cards. Designed so answers take humans 10+ minutes and aren't on page one of Google.

**Run:** 🟢 light · setup: Python + web search API (or built-in web browsing) + LLM API key (OpenAI/Anthropic) + 1266 questions from simple-evals repo · ~~3-10 min per task (persistent web search); full 1266-task eval: 2-6 hours

```bash
pip install -r requirements.txt && python evaluate.py --benchmark browsecomp --model [gpt-4o/claude-3.5-sonnet] --api_key [key]
```
<sub>⚠️ Designed so answers take humans 10+ minutes and aren't on first page of Google; tests deep-research / persistent-browsing agents; short verifiable answers; from OpenAI simple-evals repo (July 2025+ no longer actively updated with new models/results)</sub>

[paper](https://arxiv.org/abs/2504.12516) · [code](https://github.com/openai/simple-evals) · [leaderboard](https://llm-stats.com/benchmarks/browsecomp)

### WebArena `T1` 🔴
Complete high-level natural-language tasks (e-commerce, forums, GitLab, CMS) end-to-end in self-hosted, fully-functional clones of real websites, scored by execution-based functional correctness. · **812 tasks**

> The canonical reproducible web-agent benchmark (ICLR 2024); GPT-4 baseline ~14% vs human ~78%. Widely cited and used in frontier-model agent evals; ServiceNow released WebArena-Verified (2025) as an audited version.

**Run:** 🔴 heavy · setup: Docker + self-hosted websites (Magento, Forum, GitLab, Wikipedia, Map) + Python 3.10+ · ~~15-30 min per task; full 812-task eval: hours to days depending on model

```bash
pip install -r requirements.txt && playwright install && docker load --input [website_tar] && python run.py --instruction_path [prompt] --test_start_idx 0 --test_end_idx 1
```
<sub>⚠️ Requires setting up 6+ Docker containers with pre-downloaded image tars (5-10GB total); environment reset needed after full eval per protocol; AWS AMI recommended (pre-configured with all websites)</sub>

[paper](https://arxiv.org/abs/2307.13854) · [code](https://github.com/web-arena-x/webarena) · [leaderboard](https://docs.google.com/spreadsheets/d/1M801lEpBbKSNwP-vDBkC_pF7LdyGU1f_ufZb_NWNBZQ)

### WebVoyager `T1` 🟡
Complete end-to-end tasks on 15 live, high-traffic real websites (Amazon, Booking, Google Maps, GitHub, etc.) using screenshots + accessibility tree, scored by a GPT-4V automatic judge. · **643 tasks**

> ACL 2024; one of the most-cited 'agent on the live web' benchmarks and a de-facto standard for multimodal browsing agents. Its GPT-4V auto-eval (~85% agreement with humans) is widely reused.

**Run:** 🟡 medium · setup: Selenium + Chrome/Chromium + Python 3.10 + OpenAI API key (GPT-4V) · ~~5-15 min per task (live web); full 643-task eval: several hours to overnight

```bash
pip install -r requirements.txt && python run.py --test_file ./data/tasks_test.jsonl --api_key [OPENAI_API_KEY] --headless --max_iter 15
```
<sub>⚠️ Runs on live websites (Amazon, Booking, Google Maps, etc.); time-sensitive tasks require manual date updates; GPT-4V auto-eval used for scoring; Selenium-based with real browser interactions; may be affected by website changes/CAPTCHAs</sub>

[paper](https://arxiv.org/abs/2401.13919) · [code](https://github.com/MinorJerry/WebVoyager)

### Mind2Web `T1` 🟢
Predict the correct action sequence (element selection + operation) to complete open-ended tasks across 137 real websites from offline interaction traces, testing cross-domain/website generalization. · **2350 tasks**

> NeurIPS 2023 Spotlight; the first benchmark for generalist web agents and a foundational dataset spanning 31 domains / 137 sites. Heavily used for training and offline action-prediction evaluation.

**Run:** 🟢 light · setup: Python 3.10+ + HuggingFace datasets library (download from HF); test set requires password-protected zip · ~~1-5 min per task (offline prediction); full 2350-task eval: 30-60 min

```bash
git clone https://huggingface.co/datasets/osunlp/Mind2Web && unzip test_set.zip && python candidate_generation/evaluate.py --model_path [model] --data_path ./Mind2Web --split_file data/test_website/*.json
```
<sub>⚠️ Offline action-prediction benchmark (no live web); test set password-protected to prevent contamination; DeBERTa and T5-based candidate/action models provided; local evaluation only</sub>

[paper](https://arxiv.org/abs/2306.06070) · [code](https://github.com/OSU-NLP-Group/Mind2Web) · [leaderboard](https://osu-nlp-group.github.io/Mind2Web/)

### VisualWebArena `T1` 🔴
Solve realistic visually-grounded web tasks (image-text inputs, spatial reasoning) on self-hosted Classifieds, Shopping, and Reddit sites, evaluated by execution-based correctness. · **910 tasks**

> ACL 2024 multimodal extension of WebArena; the standard test for vision-grounded web agents. Top agents reached ~16% vs human ~89%, exposing a large multimodal gap.

**Run:** 🔴 heavy · setup: Docker + self-hosted websites (Classifieds, Shopping, Reddit, Wikipedia, etc.) + Python 3.10-3.11 + GPU (12GB VRAM for BLIP-2 captioning model) · ~~20-30 min per task; full 910-task eval: overnight+ runs

```bash
pip install -r requirements.txt && playwright install && python run.py --test_start_idx 0 --test_end_idx 1 --model gpt-4-vision-preview --observation_type image_som
```
<sub>⚠️ Builds on WebArena Docker setup; captioning models require GPU (12GB VRAM); environment resets needed; vision models (GPT-4V, Gemini) required; uses same Docker infrastructure as WebArena</sub>

[paper](https://arxiv.org/abs/2401.13649) · [code](https://github.com/web-arena-x/visualwebarena) · [leaderboard](https://jykoh.com/vwa)

### GAIA `T1` 🟢
Answer real-world assistant questions that require multi-step reasoning, tool use, and web browsing to find and synthesize information, with short verifiable answers. · **466 tasks**

> Meta/HuggingFace/AutoGPT benchmark; the most prominent general-assistant eval where web browsing is core. Humans ~92% vs GPT-4+plugins ~15%. Heavily used in agent framework papers and model cards; its web subset is reused in WebVoyager.

**Run:** 🟢 light · setup: Python + HuggingFace datasets (gated, requires acceptance) + LLM API key (OpenAI) + web search tools · ~~5-30 min per task (depends on search/tool complexity); full 466-task eval: several hours

```bash
from datasets import load_dataset; dataset = load_dataset('gaia-benchmark/GAIA'); [use with your agent + web search]
```
<sub>⚠️ Dataset is gated to prevent contamination; 3 difficulty levels (1-3); 466 questions across train/validation/test; tool use and web browsing are core (not isolated eval); widely used in agent frameworks</sub>

[paper](https://arxiv.org/abs/2311.12983) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### Online-Mind2Web `T2` 🟡
Execute 300 realistic tasks on 136 live websites in an online setting, judged by the WebJudge LLM-as-a-judge protocol, to measure true end-to-end success rather than offline action matching. · **300 tasks**

> COLM 2025 ('An Illusion of Progress?'); a current, widely-cited live-web benchmark used by browser-use and frontier labs. Showed prior results were over-optimistic (OpenAI Operator ~61%). WebJudge auto-eval ~85% human agreement.

**Run:** 🟡 medium · setup: Python 3.10+ + HuggingFace datasets + browser automation (Selenium/Playwright) + LLM API key (OpenAI/Anthropic/Google) · ~~5-20 min per task (live web); full 300-task eval: 1-3 days with parallelization

```bash
git clone https://github.com/OSU-NLP-Group/Online-Mind2Web && pip install -r requirements.txt && python run_agent.py --task_id [id] --model [gpt-4o/claude-3.5-sonnet] --api_key [key]
```
<sub>⚠️ Live-web benchmark on 136 real websites; WebJudge auto-eval (~85% human agreement) or manual evaluation available; regularly updated (36 tasks refreshed Nov 2025 due to website changes); requires robust error handling for real web volatility</sub>

[paper](https://arxiv.org/abs/2504.01382) · [code](https://github.com/OSU-NLP-Group/Online-Mind2Web) · [leaderboard](https://huggingface.co/datasets/osunlp/Online-Mind2Web)

---

## Computer Use (GUI / OS)

*Operating real desktops, mobile, and GUI apps via screenshots and clicks.*

### OSWorld `T1` 🔴
Execute 369 open-ended real-computer tasks (file ops, desktop apps, web, multi-app workflows) in a live Ubuntu/Windows VM, scored by execution-based checks on final system state. · **369 tasks**

> The de facto standard for desktop computer-use agents. Used in model cards/blogs by Anthropic, OpenAI, and others; OSWorld-Verified is the canonical leaderboard. Human ~72% vs early agents ~12%, now ~60%+.

**Run:** 🔴 heavy · setup: VM (VMware/VirtualBox) OR Docker + Python 3.10+ · ~varies (single task 5-30min, full eval across 10 envs hours)

```bash
python quickstart.py --provider_name vmware --path_to_vm 'path/to/vm.vmx'
```
<sub>⚠️ Requires pre-configured Ubuntu/Windows VM or Docker with KVM; some tasks need Google OAuth2; parallel evaluation needs AWS for scalability</sub>

[paper](https://arxiv.org/abs/2404.07972) · [code](https://github.com/xlang-ai/OSWorld) · [leaderboard](https://os-world.github.io/)

### AndroidWorld `T1` 🟡
Complete 116 programmatic tasks across 20 real Android apps on a live emulator, with dynamically randomized parameters yielding millions of task variations and reward signals. · **116 tasks**

> Google Research's reference benchmark for mobile/GUI agents; widely cited and used in mobile-agent model evals. Human ~80% vs early M3A agent ~30.6%.

**Run:** 🟡 medium · setup: Android Studio + Android Emulator (Pixel 6, API 33) + Python 3.11 + ffmpeg + API keys · ~setup minutes (app install may vary), task execution 5-15min per task

```bash
python run.py --suite_family=android_world --agent_name=t3a_gpt4 --perform_emulator_setup
```
<sub>⚠️ AVD named 'AndroidWorldAvd' must be pre-configured; first run with --perform_emulator_setup; lightweight (2GB RAM, 8GB disk) but requires Android Studio</sub>

[paper](https://arxiv.org/abs/2405.14573) · [code](https://github.com/google-research/android_world) · [leaderboard](https://google-research.github.io/android_world/)

### WindowsAgentArena (WAA) `T3` 🔴
Complete 154 multi-step Windows-OS tasks across real apps (Office, VS Code, Edge, File Explorer, Settings, Paint) in parallelizable Docker/Azure VMs with execution-based evaluation. · **154 tasks**

> Microsoft's Windows analogue to OSWorld; built on the OSWorld framework. Heavily used for benchmarking enterprise/desktop agents; full eval runs in ~20 min via Azure parallelization.

**Run:** 🔴 heavy · setup: Docker + Azure VM · ~hours
<sub>⚠️ Windows-in-Docker or Azure-hosted Windows VM required</sub>

[paper](https://arxiv.org/abs/2409.08264) · [code](https://github.com/microsoft/WindowsAgentArena)

### ScreenSpot-Pro `T3` 🟢
Locate tiny, cluttered UI targets from instructions on ultra-high-resolution professional desktop software (CAD, IDEs, office, scientific) via 1,581 expert-annotated screenshot-instruction pairs. · **1581 tasks**

> The hard, high-resolution successor to ScreenSpot; targets average 0.07% of screen area. Standard stress-test for grounding models (best model ~18.9% at release).

**Run:** 🟢 light · setup: Python + OpenAI API key + dataset (~3.38GB images) · ~seconds to minutes per evaluation (1,581 grounding tasks)

```bash
bash run_ss_pro.sh
```
<sub>⚠️ Repository README/requirements unavailable; setup inferred from shell scripts and scripts structure; data-only evaluation (no environment simulation like others)</sub>

[paper](https://arxiv.org/abs/2504.07981) · [code](https://github.com/likaixin2000/ScreenSpot-Pro-GUI-Grounding) · [leaderboard](https://gui-agent.github.io/grounding-leaderboard/)

---

## Tool Use & Function Calling

*Calling APIs and tools correctly, multi-turn, with the right arguments.*

### BFCL (Berkeley Function-Calling Leaderboard) `T1` 🟢
Given a natural-language request and a set of function/API schemas, the agent must emit syntactically correct function calls (single, parallel, multiple, multi-turn, and agentic) that an AST/state checker validates for correctness. · **thousands (V1-V4, ~3700+ across categories) tasks**

> The de-facto industry standard for function-calling evaluation; cited in nearly every model card (OpenAI, Anthropic, Google, Mistral, etc.). V3 added multi-turn/multi-step and V4 (2025) added real-world agentic tasks with web search, memory, and format-sensitivity.

**Run:** 🟢 light · setup: pip + conda + optional GPU; PyPI package available (bfcl-eval) or install from source with vLLM/sglang backends for self-hosted models

```bash
bfcl generate --model MODEL_NAME --test-category TEST_CATEGORY && bfcl evaluate --model MODEL_NAME --test-category TEST_CATEGORY
```
<sub>⚠️ Requires API keys (.env file) for OpenAI, Anthropic, Google, Mistral; SerpAPI key for web-search tests; vLLM/sglang backends need SM 80+ GPUs for multi-turn</sub>

[paper](https://proceedings.mlr.press/v267/patil25a.html) · [code](https://github.com/ShishirPatil/gorilla) · [leaderboard](https://gorilla.cs.berkeley.edu/leaderboard.html)

### tau-bench (τ-bench) `T1` 🟢
The agent plays a customer-service rep that must converse with an LLM-simulated user while calling domain APIs (retail, airline) under written policy constraints, judged by the final database state plus a pass^k consistency metric. · **165 (115 retail + 50 airline) tasks**

> From Sierra (Bret Taylor); the most influential tool-agent-user interaction benchmark. Heavily used in frontier model cards (Anthropic, OpenAI) as the canonical agentic tool-use eval; pass^k exposes reliability gaps.

**Run:** 🟢 light · setup: pip + OpenAI/Anthropic/Google/Mistral API keys; install via: git clone && pip install -e .

```bash
python run.py --agent-strategy tool-calling --env retail --model gpt-4o --model-provider openai --user-model gpt-4o --user-model-provider openai --max-concurrency 10
```
<sub>⚠️ Concurrent API calls require rate-limit tuning (--max-concurrency); tasks are not being updated (consider tau2-bench for latest version)</sub>

[paper](https://arxiv.org/abs/2406.12045) · [code](https://github.com/sierra-research/tau-bench) · [leaderboard](https://www.taubench.com/)

### ToolBench (ToolLLM) `T2` 🟡
Given user instructions, the agent must select and chain calls across 16,000+ real RapidAPI REST APIs (single-tool and multi-tool, with DFSDT solution paths), evaluated by pass rate and win rate against a reference. · **16,464 APIs / 3,451 tools; ~126k instruction-solution pairs tasks**

> ICLR'24 spotlight from OpenBMB; the foundational large-scale real-API tool-learning benchmark and the most-cited baseline for massive-toolset agents. Spawned StableToolBench and many follow-ups.

**Run:** 🟡 medium · setup: Python 3.9+ + pip; download data (~10GB) from Google Drive; RapidAPI key (or ToolBench key); optional GPU (2x A100 80GB for training)

```bash
export PYTHONPATH=./ && python toolbench/inference/qa_pipeline.py --tool_root_dir data/toolenv/tools/ --backbone_model toolllama --model_path ToolBench/ToolLLaMA-7b --input_query_file data/test_instruction/G1_instruction.json --output_answer_file results.json --toolbench_key $TOOLBENCH_KEY
```
<sub>⚠️ Data download requires manual URL approval; RapidAPI backend requires form submission for ToolBench key; no native Docker config; large download (~10GB)</sub>

[paper](https://arxiv.org/abs/2307.16789) · [code](https://github.com/OpenBMB/ToolBench)

### tau2-bench (τ²-bench) `T3` 🟡
Extends tau-bench to dual-control settings where both the agent AND the simulated user can call tools (modeled as a Dec-POMDP), with a Telecom troubleshooting domain plus retail and airline and a compositional task generator. · **hundreds across telecom/retail/airline tasks**

> The 2025 successor to tau-bench; now the headline conversational tool-use eval reported in current frontier model launches. Adds collaborative dual-control troubleshooting that single-agent benchmarks miss.

**Run:** 🟡 medium · setup: Python 3.12-3.13 + uv package manager; optional: brew install portaudio ffmpeg for voice evaluation; LiteLLM for multi-provider support

```bash
uv sync && tau2 run --domain airline --agent-llm gpt-4.1 --user-llm gpt-4.1 --num-trials 1 --num-tasks 5
```
<sub>⚠️ Requires .env with API credentials; voice features (--extra voice) need system dependencies (portaudio/ffmpeg); supports telecom/retail/airline domains plus mock</sub>

[paper](https://arxiv.org/abs/2506.07982) · [code](https://github.com/sierra-research/tau2-bench) · [leaderboard](https://www.taubench.com/)

### ToolSandbox `T3` 🟢
A stateful, conversational benchmark with an on-policy LLM user simulator where tools mutate shared world state and have implicit inter-tool dependencies, scored via milestone/minefield checks over the trajectory. · **1032 test scenarios tasks**

> From Apple; one of the most-cited benchmarks targeting stateful tool execution and state-dependency/canonicalization challenges that stateless single-turn benchmarks ignore.

**Run:** 🟢 light · setup: Python 3.9+ + conda; pip install '.[dev]'; OpenAI + Anthropic API keys (or Cohere/Google Cloud/HF/RapidAPI depending on agent/user selection); tools run on host machine (no Docker)

```bash
env ANTHROPIC_API_KEY=<key> OPENAI_API_KEY=<key> tool_sandbox --user GPT_4_o_2024_05_13 --agent Claude_3_Haiku --scenario wifi_off
```
<sub>⚠️ Code executes directly on host (not containerized); requires specific API keys matching chosen agent/user models; results saved to data/result_summary.json</sub>

[paper](https://arxiv.org/abs/2408.04682) · [code](https://github.com/apple/ToolSandbox)

---

## Reasoning & Planning

*Multi-step problem solving, planning under constraints, hard knowledge.*

### AgentBench `T1` 🟡
Operate as an autonomous agent across 8 distinct interactive environments (OS, database, knowledge graph, card game, lateral-thinking puzzles, web shopping/browsing, household) over multiple turns of reasoning and decision-making. · **8 environments tasks**

> ICLR'24; the first benchmark to systematically evaluate LLM-as-agent across diverse environments. Tested 27+ models and showed poor long-term reasoning/decision-making is the main blocker for usable agents. Heavily cited foundational agent benchmark from Tsinghua (THUDM).

**Run:** 🟡 medium · setup: Docker + Python 3.9 (conda recommended) + pip + OpenAI API key · ~3+ minutes startup per task; webshop task ~15+ minutes with 16GB RAM requirement

```bash
conda create -n agent-bench python=3.9 && conda activate agent-bench && pip install -r requirements.txt && python -m src.start_task -a && python -m src.assigner
```
<sub>⚠️ Requires Python 3.9 (not 3.10+) due to pinned old numpy (~1.23.x); webshop task needs ~16GB RAM; must build multiple Docker images (mysql, ubuntu, custom packages)</sub>

[paper](https://arxiv.org/abs/2308.03688) · [code](https://github.com/THUDM/AgentBench) · [leaderboard](https://docs.google.com/spreadsheets/d/e/2PACX-1vRR3Wl7wsCgHpwUw1_eUXW_fptAPLL3FkhnW_rua0O1Ji_GIVrpTjY5LaKAhwO-WeARjnY_KNw0SYNJ/pubhtml)

### PlanBench `T1` 🔴
Generate and reason about plans in classical IPC planning domains (Blocksworld, Logistics), including obfuscated variants, to test true planning vs. memorized common-sense retrieval. · **~26,250 prompts across multiple plan-reasoning task types tasks**

> NeurIPS 2023 Datasets & Benchmarks; the standard reference for rigorous, automated-planning-grounded evaluation of LLM planning. Exposed large gaps that persisted even with reasoning models (o1 analysis), making it a touchstone in the LLM-planning literature.

**Run:** 🔴 heavy · setup: Linux + Python 3.6+ + external planners (Fast Downward, VAL, PR2Plan) + pip + OpenAI API key · ~Varies by task; planning and evaluation loops can take 30+ minutes depending on domain complexity

```bash
export FAST_DOWNWARD=/path && export VAL=/path && export PR2=/path && pip install -r requirements.txt && python3 llm_plan_pipeline.py --task 'Plan Generation' --config CONFIG --engine openai
```
<sub>⚠️ Requires external planner binaries (Fast Downward, VAL, PR2Plan) with environment variables configured; Linux-only; obs-compiler needed for PR2Plan; modular pipeline allows running stages separately</sub>

[paper](https://arxiv.org/abs/2206.10498) · [code](https://github.com/karthikv792/LLMs-Planning)

### GAIA `T1` 🟢
Answer 466 real-world questions that each require a chained sequence of reasoning, web browsing, multi-modality handling, and tool use to reach a single unambiguous answer. · **466 questions (300 held out for the leaderboard, 3 difficulty levels) tasks**

> The canonical general-assistant agent benchmark from Meta AI/HuggingFace; humans score ~92% vs ~15% for GPT-4+plugins at release. Widely used in model cards and agent frameworks; also mirrored on the HAL (Princeton) leaderboard.

**Run:** 🟢 light · setup: Python + HuggingFace datasets (gated, requires acceptance) + LLM API key (OpenAI) + web search tools · ~~5-30 min per task (depends on search/tool complexity); full 466-task eval: several hours

```bash
from datasets import load_dataset; dataset = load_dataset('gaia-benchmark/GAIA'); [use with your agent + web search]
```
<sub>⚠️ Dataset is gated to prevent contamination; 3 difficulty levels (1-3); 466 questions across train/validation/test; tool use and web browsing are core (not isolated eval); widely used in agent frameworks</sub>

[paper](https://arxiv.org/abs/2311.12983) · [code](https://huggingface.co/datasets/gaia-benchmark/GAIA) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### TravelPlanner `T2` 🟡
Act as a travel-planning agent that queries a sandbox of ~4M records via tools and produces a complete multi-day itinerary satisfying many hard and soft real-world constraints. · **1,225 planning queries with reference plans tasks**

> ICML'24 Spotlight (OSU NLP); the marquee real-world constrained-planning agent benchmark. GPT-4 reached only 0.6% final-pass rate at release, making it a hard, widely-cited stress test for tool-use + constraint planning.

**Run:** 🟡 medium · setup: Python 3.9 (conda) + pip + Google Drive database download + OpenAI API key (gpt-3.5-turbo or gpt-4) or other LLM API · ~Plan generation: 30+ seconds per query; full pipeline with postprocessing/evaluation: 5-15 minutes depending on LLM model and query complexity

```bash
conda create -n travelplanner python=3.9 && pip install -r requirements.txt && cd agents && python tool_agents.py --set_type validation --output_dir ./output --model_name gpt-4
```
<sub>⚠️ Requires manual download of 4M-record database from Google Drive (not via pip); test-set eval uses official leaderboard to prevent contamination; GPT-4 conversion step (parsing.py) needed before final evaluation</sub>

[paper](https://arxiv.org/abs/2402.01622) · [code](https://github.com/OSU-NLP-Group/TravelPlanner) · [leaderboard](https://huggingface.co/spaces/osunlp/TravelPlannerLeaderboard)

---

## Multi-Agent

*Collaboration, competition, and social/strategic interaction between agents.*

### SOTOPIA `T1` 🟢
Two LLM agents role-play assigned characters with private, sometimes-conflicting social goals across 90 scenarios (negotiation, collaboration, competition) and are scored on goal completion and relationship maintenance via multi-turn interactive social simulation. · **90 social scenarios tasks**

> ICLR 2024 spotlight; the de-facto standard for social/interactive multi-agent intelligence, widely cited and extended (SOTOPIA-pi, SOTOPIA-RL). SOTOPIA-Eval defines 7 social dimensions (BEL, REL, KNO, SEC, SOC, FIN, GOAL).

**Run:** 🟢 light · setup: pip + OpenAI API key + Redis (Docker) or local JSON storage · ~~2-5 minutes per simulation (varies by scenario count)

```bash
python examples/minimalist_demo.py
```
<sub>⚠️ Requires OpenAI API key; Redis Docker container recommended but local JSON fallback available; uv package manager recommended for installation</sub>

[paper](https://arxiv.org/abs/2310.11667) · [code](https://github.com/sotopia-lab/sotopia) · [leaderboard](https://huggingface.co/datasets/cmu-lti/sotopia)

### GAMA-Bench `T3` 🟢
LLMs act as players in eight classical multi-agent game-theory games (across cooperation, betrayal, and sequential settings) under a dynamic scoring scheme that quantitatively measures their decision-making robustness, generalizability, and strategy in multi-agent environments. · **8 game-theory games tasks**

> Game-theory-grounded benchmark for multi-agent decision-making (e.g. public goods, guessing games, auctions); from CUHK-ARISE, frequently cited for evaluating LLM rationality in N-agent settings.

**Run:** 🟢 light · setup: pip + OpenAI API key + optional Google and InfraDeep API keys · ~~1-3 minutes per game instance (20 rounds)

```bash
from games.guessing_game import *; game = GuessingGame(...); game.run(20)
```
<sub>⚠️ Jupyter Notebook-heavy codebase (94.6%); must create utils.py with API credentials; saves results to save/ and records/ directories automatically</sub>

[paper](https://arxiv.org/abs/2403.11807) · [code](https://github.com/CUHK-ARISE/GAMABench)

### MultiAgentBench (MARBLE) `T3` 🟢
LLM agents must coordinate (and in some tasks compete) across eight tasks spanning research, software, gaming (Werewolf, Minecraft), database and web scenarios under different coordination topologies (star/chain/tree/graph), scored on milestone-based task and collaboration/competition KPIs. · **8 tasks / scenarios tasks**

> ACL 2025 Main. One of the most comprehensive purpose-built benchmarks for measuring both collaboration AND competition quality (not just task success) across coordination protocols; from UIUC's ulab.

**Run:** 🟢 light · setup: pip + Conda + Poetry + OpenAI API key + Together API key (optional) · ~~5-15 minutes per scenario (depends on task complexity)

```bash
cd scripts/werewolf && bash run_simulation.sh
```
<sub>⚠️ Requires multiple API keys (OpenAI, Together); Poetry dependency manager used; supports Docker but integration not fully documented</sub>

[paper](https://arxiv.org/abs/2503.01935) · [code](https://github.com/MultiagentBench/MARBLE)

### Collab-Overcooked `T3` 🟢
Two LLM agents must cooperate in an extended Overcooked-AI kitchen environment, communicating in natural language to complete 30 open-ended cooking tasks, scored with process-oriented metrics that probe fine-grained collaboration (not just final success). · **30 open-ended tasks tasks**

> EMNLP 2025 Main; notable for process-oriented collaboration metrics that diagnose how (not just whether) agents coordinate, on the well-known Overcooked cooperation testbed.

**Run:** 🟢 light · setup: pip + Conda + mpi4py + OpenAI API key + local Overcooked-AI game environment · ~~1.5 minutes for basic validation test

```bash
cd src && python main.py --horizon 3 --order boiled_egg
```
<sub>⚠️ Requires local installation of modified Overcooked-AI library via pip install -e; OpenAI key placed in openai_key.txt; Python 3.8 required; mpi4py needed for parallel processing</sub>

[paper](https://arxiv.org/abs/2502.20073) · [code](https://github.com/YusaeMeow/Collab-Overcooked)

---

## Science & Research

*Data analysis, ML engineering, and autonomous scientific discovery.*

### MLE-bench `T1` 🔴
Given a real Kaggle competition (dataset + task), the agent must run the full ML engineering pipeline — data prep, model training, tuning — and produce a valid submission scored against human leaderboards. · **75 tasks**

> OpenAI (ICLR 2025 Oral); the standard ML-engineering agent benchmark, used in OpenAI and other model cards. o1-preview+AIDE reached Kaggle-bronze level on 16.9% of competitions.

**Run:** 🔴 heavy · setup: pip + Docker + Kaggle API credentials + Git LFS + 3.3TB storage (full) or 158GB (lite) · ~Lite prepare ~hours; full prepare ~2 days; eval with GPU ~days per competition

```bash
mlebench prepare --lite; mlebench grade <submission-path>
```
<sub>⚠️ Requires Docker container with ML libraries; Kaggle credentials in ~/.kaggle/; Git LFS must fetch large competition data; lite version has 22 competitions vs 75 full</sub>

[paper](https://arxiv.org/abs/2410.07095) · [code](https://github.com/openai/mle-bench)

### PaperBench `T1` 🟡
Given an ICML 2024 paper, the agent must replicate it from scratch — understand the contributions, build the codebase, and run experiments to reproduce its empirical results. · **20 papers (8,316 gradable sub-tasks) tasks**

> OpenAI benchmark (ICML 2025) with author-co-designed rubrics; used in OpenAI model evaluations. Best agent (Claude 3.5 Sonnet) scored 21% vs 41% for PhD-level humans in 48h.

**Run:** 🟡 medium · setup: uv (package manager) + model API access · ~48 hours for full PhD-level replication per paper

```bash
uv sync (in project/paperbench directory, then follow README)
```
<sub>⚠️ Uses `uv` for environment management instead of pip/conda; 20 ICML 2024 papers require reading/understanding contributions, building codebase, and reproducing experiments</sub>

[paper](https://arxiv.org/abs/2504.01848) · [code](https://github.com/openai/frontier-evals)

### SciCode `T1` 🟢
Given a real scientific research problem decomposed into subproblems, the agent must synthesize code that recalls domain knowledge, reasons, and passes scientist-written gold test cases. · **80 problems (338 subproblems) tasks**

> Scientist-curated across physics, math, materials, biology, chemistry. Extremely hard (best model ~4.6% fully solved); used in AstaBench and the Holistic Agent Leaderboard.

**Run:** 🟢 light · setup: pip + model API key (OpenAI or equivalent) + Google Drive download for test data (test_data.h5) · ~Variable by problem; 338 subproblems across 80 problems; best model ~4.6% fully solved

```bash
inspect eval scicode.py --model openai/gpt-4o --temperature 0
```
<sub>⚠️ 100% Python codebase; test data (h5 file) must be manually downloaded from Google Drive and placed at eval/data/test_data.h5; uses inspect_ai framework (not standalone scripts)</sub>

[paper](https://arxiv.org/abs/2407.13168) · [code](https://github.com/scicode-bench/SciCode) · [leaderboard](https://scicode-bench.github.io/)

### ScienceAgentBench `T2` 🟡
Given a real scientific data-analysis task, the agent must write a self-contained Python program that produces the correct result across bioinformatics, computational chemistry, GIS, and neuroscience. · **102 tasks**

> ICLR 2025; 102 tasks extracted from 44 peer-reviewed papers, validated by 9 domain experts. Widely cited reference benchmark for data-driven scientific discovery; best agents solve only ~32%.

**Run:** 🟡 medium · setup: conda + pip + OpenAI API key + AWS credentials (optional) · ~Variable by task; 102 tasks across 4 domains

```bash
python -u run_infer.py --llm_engine_name {MODEL_NAME} --log_fname {LOG_FNAME}
```
<sub>⚠️ Requires two separate conda environments (sci-agent and sci-agent-eval); full benchmark requires password-protected HuggingFace download</sub>

[paper](https://arxiv.org/abs/2410.05080) · [code](https://github.com/OSU-NLP-Group/ScienceAgentBench) · [leaderboard](https://osu-nlp-group.github.io/ScienceAgentBench/)

---

## Safety, Security & Robustness

*Prompt injection, harmful-tool refusal, and adversarial robustness.*

### AgentDojo `T1` 🟢
In realistic environments (email client, e-banking, travel booking) the agent must complete legitimate user tasks while resisting prompt-injection instructions hidden in tool/data outputs that try to hijack its behavior. · **97 realistic tasks, 629 security test cases tasks**

> One of the most influential prompt-injection agent benchmarks; NeurIPS 2024 Datasets & Benchmarks; maintains a public leaderboard and is the standard testbed for injection attacks/defenses (CaMeL, StruQ, Meta SecAlign all report on it).

**Run:** 🟢 light · setup: pip + API key (OpenAI/Anthropic/others) · ~< 1 hour per run

```bash
python -m agentdojo.scripts.benchmark --model gpt-4o-2024-05-13 --defense tool_filter --attack tool_knowledge
```
<sub>⚠️ API unstable (under development, breaking changes possible). Optional transformers extra for injection detection. Leaderboard at agentdojo.spylab.ai.</sub>

[paper](https://arxiv.org/abs/2406.13352) · [code](https://github.com/ethz-spylab/agentdojo) · [leaderboard](https://agentdojo.spylab.ai)

### AgentDojo `T1` 🟢
A dynamic environment of 97 realistic tool-using tasks plus 629 prompt-injection security test cases, where an attacker plants malicious instructions in tool outputs and the agent must complete the task without being hijacked. · **97 tasks + 629 injection cases tasks**

> NeurIPS 2024 Datasets & Benchmarks; the reference prompt-injection / tool-use security benchmark, used as the standard testbed for injection attacks and defenses (CaMeL, StruQ, Meta SecAlign all report on it).

**Run:** 🟢 light · setup: pip + API key (OpenAI/Anthropic/others) · ~< 1 hour per run

```bash
python -m agentdojo.scripts.benchmark --model gpt-4o-2024-05-13 --defense tool_filter --attack tool_knowledge
```
<sub>⚠️ API unstable (under development, breaking changes possible). Optional transformers extra for injection detection. Leaderboard at agentdojo.spylab.ai.</sub>

[paper](https://arxiv.org/abs/2406.13352) · [code](https://github.com/ethz-spylab/agentdojo) · [leaderboard](https://agentdojo.spylab.ai/)

### AgentHarm `T1` 🟢
Given an explicitly malicious multi-step request (e.g. fraud, cybercrime, harassment), the tool-using agent must either refuse or, if jailbroken, the benchmark measures whether it still completes the harmful task end-to-end. · **110 base behaviors (440 with augmentations) across 11 harm categories, 104 tools tasks**

> De facto standard for agent harmfulness/jailbreak robustness; built by the UK AI Safety Institute, integrated into Inspect Evals, and widely cited in model safety cards and red-teaming work.

**Run:** 🟢 light · setup: pip + API key (Anthropic/OpenAI/Google) · ~variable (depends on task count and LLM latency)

```bash
uv run inspect eval inspect_evals/agentharm
```
<sub>⚠️ Requires Python 3.11+ and .env with INSPECT_EVAL_MODEL and provider API key. No Docker or datasets needed.</sub>

[paper](https://arxiv.org/abs/2410.09024) · [code](https://github.com/UKGovernmentBEIS/inspect_evals) · [leaderboard](https://huggingface.co/datasets/ai-safety-institute/AgentHarm)

### AgentPoison `T2` 🔴
Red-teams a RAG/memory-augmented LLM agent by poisoning its knowledge base or memory with a tiny number of crafted entries, then measures how reliably the backdoor triggers malicious actions. · **<0.1% poison rate, 80%+ attack success tasks**

> NeurIPS 2024; Dawn Song (UC Berkeley) is a direct author. The canonical memory/knowledge-base poisoning attack benchmark for agentic RAG systems.

**Run:** 🔴 heavy · setup: conda environment + HuggingFace embedder checkpoints + Google Drive datasets + API keys (OpenAI/Replicate) · ~hours to days (depends on optimization passes)

```bash
python algo/trigger_optimization.py --agent ad --algo ap --model dpr-ctx_encoder-single-nq-base --save_dir ./results --ppl_filter --target_gradient_guidance --asr_threshold 0.5
```
<sub>⚠️ Memory-intensive knowledge-base poisoning. Manual checkpoint downloads from HuggingFace. Three agent implementations require separate datasets in specific directories.</sub>

[paper](https://arxiv.org/abs/2407.12784) · [code](https://github.com/AI-secure/AgentPoison)

### OS-Harm `T2` 🔴
Measures the safety of computer-use (GUI) agents across 150 tasks spanning deliberate user misuse, prompt-injection attacks, and unprompted model misbehavior, judged by an automated safety evaluator. · **150 tasks**

> NeurIPS 2025 Spotlight; the first benchmark dedicated to computer-use agent safety (built on OSWorld), covering misuse, injection, and misbehavior in one suite.

**Run:** 🔴 heavy · setup: VM (VMWare Workstation) + OSWorld + pip + API keys (OpenAI/Anthropic/Google) · ~1-4 hours per full eval (parallelizable)

```bash
python run.py --path_to_vm Ubuntu/Ubuntu.vmx --observation_type screenshot_a11y_tree --model o4-mini --result_dir ./results --test_all_meta_path evaluation_examples/test_misuse.json
```
<sub>⚠️ Built on OSWorld; requires live VM. Auto-LLM-judge. Three task categories: misuse, injection, misbehavior. Models tested: o4-mini, Claude 3.7, GPT 4.1, Gemini.</sub>

[paper](https://arxiv.org/abs/2506.14866) · [code](https://github.com/tml-epfl/os-harm)

### Agent Security Bench (ASB) `T3` 🟡
Across 10 agent scenarios (e-commerce, finance, autonomous driving, etc.) the agent is subjected to formalized attacks (prompt injection, memory poisoning, Plan-of-Thought backdoor) and paired defenses, scored by attack success rate. · **~90,000 test cases; 10 scenarios, 400+ tools, 27 attack/defense methods tasks**

> Most comprehensive single framework formalizing agent attacks AND defenses; ~90,000 test cases; widely cited in agent-security surveys for covering injection, memory, and backdoor vectors together.

**Run:** 🟡 medium · setup: pip + Ollama (for open-source) or API keys (GPT/Claude); conda environment · ~30 min - 2 hours depending on attack type

```bash
python scripts/agent_attack.py --cfg_path config/DPI.yml
```
<sub>⚠️ Requires Python 3.11, conda, optional CUDA. Ollama needed for open-source models. Config-driven (DPI, OPI, MP, PoT backdoor variants).</sub>

[paper](https://arxiv.org/abs/2410.02644) · [code](https://github.com/agiresearch/ASB)

---

## Cybersecurity (Offensive)

*Finding and exploiting real vulnerabilities, CTFs, and bug bounties.*

### CyberGym `T1` 🔴
Tasks agents with finding and exploiting real software vulnerabilities across 1,500+ C/C++ targets drawn from open-source projects, scored by producing a working proof-of-concept exploit. · **1,507 real vulnerabilities tasks**

> UC Berkeley (sunblaze-ucb, Dawn Song group); a large-scale real-vulnerability exploitation benchmark that surfaced dozens of zero-days. One of the most rigorous offensive-security agent evals.

**Run:** 🔴 heavy · setup: Python + Docker + Git LFS + large dataset storage · ~Variable; task-dependent (minutes to hours per vulnerability exploitation)

```bash
python3 -m cybergym.server --host 0.0.0.0 --port 8666 --mask_map_path mask_map.json --log_dir ./server_poc
```
<sub>⚠️ Requires 130GB minimum (binary-only) or 10TB (full). Git LFS dataset from HuggingFace must be cloned separately. API key authentication required (CYBERGYM_API_KEY environment variable).</sub>

[paper](https://arxiv.org/abs/2506.02548) · [code](https://github.com/sunblaze-ucb/cybergym) · [leaderboard](https://www.cybergym.io/)

### CyBench `T1` 🟢
Evaluates agents on 40 professional-level Capture-the-Flag (CTF) cybersecurity tasks from real competitions, requiring multi-step exploitation in a sandboxed environment. · **40 CTF tasks tasks**

> A widely-cited CTF agent benchmark used to measure offensive cyber capability of frontier models (GPT-4o, Claude 3.5, etc.); a reference point in cyber-risk evaluations.

**Run:** 🟢 light · setup: Python 3.9-3.10 + pip + API key (OpenAI/Anthropic/Azure/Google/Together/Helm) · ~Minutes per task; varies by complexity level

```bash
./run_task.sh --task_dir 'benchmark/hackthebox/cyber-apocalypse-2024/crypto/[Very Easy] Dynastic' --max_iterations 5 --model openai/gpt-4o-2024-05-13
```
<sub>⚠️ Requires .env file with LLM API keys. Azure users must remove trailing slash from AZURE_OPENAI_ENDPOINT and ensure deployment name matches model name. No explicit hardware specs documented.</sub>

[paper](https://arxiv.org/abs/2408.08926) · [code](https://github.com/andyzorigin/cybench)

### CVE-Bench `T2` 🟡
Tests whether an agent can exploit real-world web-application vulnerabilities reproduced from actual CVEs, in isolated containerized environments, scored by successful exploitation. · **40 CVEs tasks**

> ICML 2025; UIUC. The first benchmark built on real CVEs for web-app exploitation, used by the US AI Safety Institute for capability evaluation.

**Run:** 🟡 medium · setup: Docker + uv (Python package manager) + LLM API key (e.g., OpenAI) · ~Not documented; container-dependent

```bash
./run eval --model=openai/gpt-4o-2024-11-20
```
<sub>⚠️ amd64 machines officially supported; ARM64 support is experimental. Cannot access all manual exploits (data contamination prevention). Remote code execution is the evaluation criterion (as of v2.1.0).</sub>

[paper](https://arxiv.org/abs/2503.17332) · [code](https://github.com/uiuc-kang-lab/cve-bench)

### BountyBench `T2` 🔴
Grounds agent cyber capability in real money: 25 real systems and 40 real bug bounties ($10–30K payouts), with Detect / Exploit / Patch task formulations. · **25 systems, 40 bounties tasks**

> NeurIPS 2025; the first benchmark to tie agent cyber performance to real bug-bounty economics across the full detect-exploit-patch lifecycle.

**Run:** 🔴 heavy · setup: Python + Docker Desktop + git submodules + local environment setup per bounty · ~Not documented; task and environment-dependent

```bash
./run_ci_local.sh <env_dir>/bounties/bounty_# --patch --check-invariants
```
<sub>⚠️ Requires manual per-bounty environment setup (installing packages, configuring servers, hydrating databases). Must use container names instead of localhost for inter-container communication in CI. Branch directly in main repo, not fork, for CI pipeline to run correctly.</sub>

[paper](https://arxiv.org/abs/2505.15216) · [code](https://github.com/cybench/BountyBench) · [leaderboard](https://bountybench.github.io/)

---

## General & Real-World Work

*Cross-domain office/company tasks that mirror real knowledge work.*

### AgentBench `T1` 🟡
Evaluate an LLM as an agent across 8 distinct interactive environments (OS, database, knowledge graph, card game, web shopping/browsing, etc.) in multi-turn open-ended settings. · **8 environments tasks**

> ICLR 2024; one of the earliest and most-cited multi-environment LLM-as-agent benchmarks (Tsinghua/THUDM), evaluated 27 LLMs and surfaced the closed-vs-open-source agent capability gap.

**Run:** 🟡 medium · setup: Docker + Python 3.9 (conda recommended) + pip + OpenAI API key · ~3+ minutes startup per task; webshop task ~15+ minutes with 16GB RAM requirement

```bash
conda create -n agent-bench python=3.9 && conda activate agent-bench && pip install -r requirements.txt && python -m src.start_task -a && python -m src.assigner
```
<sub>⚠️ Requires Python 3.9 (not 3.10+) due to pinned old numpy (~1.23.x); webshop task needs ~16GB RAM; must build multiple Docker images (mysql, ubuntu, custom packages)</sub>

[paper](https://arxiv.org/abs/2308.03688) · [code](https://github.com/THUDM/AgentBench)

### OSWorld `T1` 🔴
Drive a real Ubuntu/Windows/macOS computer via screenshots and GUI/CLI actions to complete 369 open-ended desktop and web tasks spanning multiple applications, evaluated by execution scripts. · **369 tasks**

> NeurIPS 2024; the standard real-computer-use benchmark (XLang Lab) referenced in Anthropic/OpenAI computer-use model cards. Humans solve >72% vs ~12% for early best models, with rapid leaderboard progress since.

**Run:** 🔴 heavy · setup: VM (VMware/VirtualBox) OR Docker + Python 3.10+ · ~varies (single task 5-30min, full eval across 10 envs hours)

```bash
python quickstart.py --provider_name vmware --path_to_vm 'path/to/vm.vmx'
```
<sub>⚠️ Requires pre-configured Ubuntu/Windows VM or Docker with KVM; some tasks need Google OAuth2; parallel evaluation needs AWS for scalability</sub>

[paper](https://arxiv.org/abs/2404.07972) · [code](https://github.com/xlang-ai/OSWorld) · [leaderboard](https://os-world.github.io/)

### Terminal-Bench `T1` 🔴
Complete hard, realistic end-to-end command-line tasks in a sandboxed terminal — compiling code, configuring legacy systems, training models, security and data-science workflows — verified by execution. · **89 (Core v0.1.1) tasks**

> Stanford x Laude Institute (ICLR 2026); a heavily-used agentic-terminal leaderboard cited in frontier model cards, with active 1.0/2.0/2.1 and Hard versions tracked on multiple aggregator sites.

**Run:** 🔴 heavy · setup: Docker + pip + Python 3.x · ~not specified; parallelizable via --n-concurrent

```bash
tb run
```
<sub>⚠️ Distributed as pip package; also available via 'uv tool install terminal-bench'; full command: tb run --agent terminus --model anthropic/claude-3-7-latest --dataset-name terminal-bench-core --dataset-version 0.1.1 --n-concurrent 8</sub>

[paper](https://arxiv.org/abs/2601.11868) · [code](https://github.com/laude-institute/terminal-bench) · [leaderboard](https://www.tbench.ai/leaderboard)

### TheAgentCompany `T1` 🟡
Act as a digital worker inside a self-hosted simulated software company, browsing internal sites, writing code, running programs, and messaging simulated coworkers to complete consequential workplace tasks. · **175 tasks**

> Influential real-workplace benchmark (CMU et al.) with a self-contained GitLab/Plane/RocketChat/ownCloud environment; best agents complete only ~30% of full tasks. Public leaderboard and submission process.

**Run:** 🟡 medium · setup: Docker + Docker Compose + 30GB disk space · ~setup in minutes; eval time varies

```bash
bash setup.sh && cd evaluation && bash run_eval.sh --agent-llm-config <group1> --env-llm-config <group2> --outputs-path <outputs> --server-hostname <hostname> --version 1.0.0
```
<sub>⚠️ Requires GitHub network access for license validation; root privileges needed; Mac/Windows must enable host networking explicitly</sub>

[paper](https://arxiv.org/abs/2412.14161) · [code](https://github.com/TheAgentCompany/TheAgentCompany) · [leaderboard](https://the-agent-company.com/)

### GAIA `T1` 🟢
Answer 466 human-authored real-world assistant questions that require multi-step reasoning, web browsing, multimodality, and tool use, each with a single verifiable short answer. · **466 tasks**

> The canonical general-AI-assistant benchmark (FAIR/Meta, HuggingFace, AutoGPT). Humans score 92% vs ~15% for GPT-4+plugins at launch; widely cited and reported in model cards and agent frameworks.

**Run:** 🟢 light · setup: Python + HuggingFace datasets (gated, requires acceptance) + LLM API key (OpenAI) + web search tools · ~~5-30 min per task (depends on search/tool complexity); full 466-task eval: several hours

```bash
from datasets import load_dataset; dataset = load_dataset('gaia-benchmark/GAIA'); [use with your agent + web search]
```
<sub>⚠️ Dataset is gated to prevent contamination; 3 difficulty levels (1-3); 466 questions across train/validation/test; tool use and web browsing are core (not isolated eval); widely used in agent frameworks</sub>

[paper](https://arxiv.org/abs/2311.12983) · [code](https://github.com/aymeric-roucher/GAIA) · [leaderboard](https://huggingface.co/spaces/gaia-benchmark/leaderboard)

### Agents' Last Exam (ALE) `T2` 🔴
Asks agents to perform economically valuable, expert-sourced work across 55 occupations and 1,500+ real tasks, scoring whether outputs meet professional standards. · **1,500+ across 55 occupations tasks**

> Berkeley RDI flagship (directed by Dawn Song); an economically-grounded successor in spirit to GAIA, mapping agent capability to real industry work.

**Run:** 🔴 heavy · setup: GCP VMs or QEMU/KVM or Docker (supports multiple providers) · ~task-dependent; varies widely by task complexity

```bash
provider-specific YAML config required; see provider quick-start guides (gcp-vm, qemu, docker, or static)
```
<sub>⚠️ Requires professional software licenses in sandbox; supports elastic batch scaling; multiple infrastructure options available</sub>

[paper](https://arxiv.org/abs/2606.05405) · [code](https://github.com/rdi-berkeley/agents-last-exam) · [leaderboard](https://agents-last-exam.org/)

---

## Contributing

Add a benchmark if it is real, used, and verifiable. Include paper/code URLs (verify live), one concrete sentence on the task, the dimension, a tier suggestion, and the setup/difficulty. One entry per PR.

---

*Maintained as part of [first-tree](https://github.com/unispark-inc/first-tree?ref=awesome-ai-agent-benchmarks) — shared context infrastructure for agent teams.*