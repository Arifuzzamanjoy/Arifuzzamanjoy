<div align="center">

# Arifuzzaman Joy

**I put LLM and AI-agent systems into production on serverless and rented GPUs,
for a fraction of what the managed APIs cost.**

<a href="https://www.upwork.com/freelancers/arifuzzamanj2"><img src="https://img.shields.io/badge/Available%20for%20work%20on%20Upwork-6FDA44?style=for-the-badge&logo=upwork&logoColor=white" alt="Upwork"></a>

[Email](mailto:joy.apee@gmail.com) · [LinkedIn](https://www.linkedin.com/in/arifuzzaman-joy-ru/) · [Portfolio](https://arifuzzamanjoy.github.io/) · [Scholar](https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en) · [Hugging Face](https://huggingface.co/Joyapeee) · [ORCID](https://orcid.org/0009-0005-2420-6585)

</div>

---

Anyone can claim GPU experience. Here's what you can click on:

| | |
|---|---|
| **14 PRs merged** into [Osmantic/ODS](https://github.com/Osmantic/ODS/pulls?q=is%3Apr+author%3AArifuzzamanjoy) | a 4.6k-star self-hosted AI server platform |
| **Merged** into [casys-kaist/LLMServingSim](https://github.com/casys-kaist/LLMServingSim/pull/59) | LLM-serving simulator from a KAIST research lab |
| **Featured extension** in [Gen-Verse/LatentMAS](https://github.com/Gen-Verse/LatentMAS#-5-latentmas-slora) | official repo of an ICML 2026 Spotlight paper |
| **5 papers, 75 citations, h-index 5** | [Google Scholar](https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en) |

---

## What I actually do all day

Most of it is unglamorous. The Dockerfile that builds on the first try. The installer that survives a Vast.ai box shipping the wrong CUDA driver. The health check that had been quietly dropping half your services since March and nobody noticed.

I came up through research before infrastructure, which mostly means I can read a paper on Monday and have it deployed by Friday instead of bookmarking it and feeling good about myself.

**People hire me to:**

- Deploy models as **serverless GPU endpoints** on RunPod, Modal, or Vast.ai. Dockerized, CI/CD, autoscaled down to near-zero idle cost.
- Build **RAG and document pipelines** that can prove they work: retrieval, citation tracking, multi-hop reasoning, LLM-as-judge evals so "it feels better" becomes a number.
- Stand up **multi-agent systems**, including latent-space designs where agents pass hidden states instead of burning tokens regenerating text.
- Serve **hot-swappable LoRA adapters** off one base model, routed by domain. I train the adapters too.
- Rescue deployments that *almost* work. Multi-GPU OOM, driver mismatch, topology-aware placement, squeezing a model onto a card that shouldn't fit it.

---

## Three things I built, and what was hard about them

### Health checks that don't lie · [ODS #1343](https://github.com/Osmantic/ODS/pull/1343)

ODS assumed every service spoke HTTP. Anything exposing only TCP or a CLI failed its health check, got marked dead, and disappeared from the dashboard without an error anyone would see. Silent data loss, basically, but for services.

I threaded a `health_type: http|tcp|none` field through the whole stack: JSON schema, catalog generator, dashboard API, and the shell scripts underneath. The interesting part wasn't the feature, it was the migration. Dozens of existing manifests had to keep working untouched, so the default had to infer correctly from what was already declared.

Same codebase, also merged: a [node diagnostics endpoint](https://github.com/Osmantic/ODS/pull/1664) for runtime hardware introspection, [`gpu_backends` schema validation](https://github.com/Osmantic/ODS/pull/646), and [compatibility blocks across 25 manifests](https://github.com/Osmantic/ODS/pull/717).

### Agents that think without talking · [LatentMAS-SLoRA](https://github.com/Arifuzzamanjoy/latent_mas_slora)

Multi-agent systems waste enormous money re-serializing thoughts into English so the next agent can re-parse them. LatentMAS (ICML 2026 Spotlight) showed you can skip that and pass hidden states directly.

I extended it with role-specialized LoRA adapters that hot-swap at runtime, so one base model plays Planner, Critic, Refiner, and Judger without four sets of weights in VRAM. Critic and Refiner never generate a token, about 200ms each. Ships with VLM support on Qwen2.5-VL-7B, RAG integration, and a RunPod serverless deployment with CI/CD.

The authors added it to their README as [community extension #5](https://github.com/Gen-Verse/LatentMAS#-5-latentmas-slora), next to work from MIT's LAMM group. [Demo video.](https://www.youtube.com/watch?v=g7sxYjwgRRk)

The README is also explicit about what it *isn't*: PEFT-based adapter management, not true S-LoRA. No custom CUDA paging kernels, no heterogeneous batching. I'd rather you read that there than discover it on a call.

### Making rented GPUs behave · [ODS #983](https://github.com/Osmantic/ODS/pull/983)

Vast.ai and similar marketplaces hand you a box that is *technically* the GPU you paid for and broken in a dozen quiet ways. Wrong driver, missing ACLs, a container runtime that isn't wired up.

I wrote a multi-phase hardened installer for it: `set -euo pipefail` throughout, hard-fail ACL checks, GPU-tier detection, and roughly 28 documented host-environment failure modes with the fix for each. That documentation was most of the value. Anyone can write the happy path.

---

## What I want to work on

I care where this ends up. My research has been in solar cell optimization and medical imaging, and the client work I chase is in health, energy, education, and scientific tooling. Good rates matter, I'm not shy about that. But I do the best work when the thing being built has some reason to exist beyond a funding round.

If that's what you're building, lead with it.

---

## Projects

| Project | What it is | Stack |
|---|---|---|
| [**LatentMAS-SLoRA**](https://github.com/Arifuzzamanjoy/latent_mas_slora) | Multi-agent reasoning, dynamic LoRA routing, latent-space collaboration | PyTorch, PEFT, Qwen2.5-VL, RunPod |
| [**gpu-broker-mcp**](https://github.com/Arifuzzamanjoy/gpu-broker-mcp) | MCP server brokering GPU compute for agents. Discover, reserve, dispatch, poll, with no SSH keys or provider APIs to manage | MCP, Python, Streamable HTTP |
| [**RAG + LLM-as-Judge Eval**](https://github.com/Arifuzzamanjoy/RAG_Chatbot_-_Evaluation_LLM_as_Judge) | Retrieval over URL/JSON/CSV with citation tracking and automated evaluation | Python, embeddings, evals |
| [**Wan 2.2 Multi-GPU**](https://github.com/Arifuzzamanjoy/Wan2.2_multigpu_runpod_gpu_with_gradio_interface_for_selfhosting_UI) | Topology-aware multi-GPU video pipeline, per-GPU VRAM capping to kill multi-GPU OOM | torch.distributed, FSDP, Gradio |
| [**FLUX.2 klein Worker**](https://github.com/Arifuzzamanjoy/flux2kleinserverless) | Serverless text-to-image and image-to-image, near-zero idle cost | RunPod, Docker, Flux |
| [**WordPress Cloner**](https://github.com/Arifuzzamanjoy/wordpress-cloner) | Async site cloner, 8-signal WP detection, REST extraction, WXR export. Packaged with tests and CI | Python, aiohttp |
| [**Whisper Worker**](https://github.com/Arifuzzamanjoy/worker-whisper) | Speech-to-text as a scalable on-demand endpoint | Whisper, RunPod |
| [**Diffusion Serverless Ecosystem**](https://github.com/Arifuzzamanjoy/image_diffusion_ecosystem_serverlesss) | End-to-end serverless diffusion inference, Dockerized with CI/CD | Diffusers, Docker |

<details>
<summary>More: LoRA training, Bangla NLP, low-VRAM inference</summary>

<br>

| Project | What it does |
|---|---|
| [Flux LoRA Studio](https://github.com/Arifuzzamanjoy/Flux.2-dev-gradio-ui-runpod-A40-48-vram--H200-vram-) | Self-hosted Flux LoRA platform, A40 48GB through H200, 4-bit quantization and batch inference |
| [Self-Hosted AI Starter Kit](https://github.com/Arifuzzamanjoy/self-hosted-ai-starter-kit-low_cost_cloud_cpu_with_external_share-) | Low-cost CPU-friendly self-hosting with secure external sharing |
| [bangladeshi-tts-finetuning](https://github.com/Arifuzzamanjoy/bangladeshi-tts-finetuning) | Fine-tuning TTS for Bangla speech |
| [bangla-punctuation-restoration](https://github.com/Arifuzzamanjoy/bangla-punctuation-restoration) | Transformer-based punctuation restoration for Bangla |
| [time-series forecasting](https://github.com/Arifuzzamanjoy/time-_series_forcasting_state-_of-_the_art) | Modern forecasting model implementations |
| [Wan2GP](https://github.com/Arifuzzamanjoy/Wan2GP) | Low-VRAM video generation for consumer GPUs |
| [Ltx-Image-to-Video](https://github.com/Arifuzzamanjoy/Ltx-Image-to-Video-GradioInterface) | Image-to-video with a Gradio interface |

</details>

---

## Stack

**GPU & serving** — RunPod, Modal, Vast.ai, vLLM, Docker, Docker Compose, torch.distributed, FSDP, 4-bit quantization

**LLM & agents** — PyTorch, Transformers, PEFT/LoRA, LangChain, MCP, RAG, LLM-as-judge evaluation, Qwen2.5-VL

**Backend & ops** — Python, FastAPI, Bash, GitHub Actions, pytest, ShellCheck, SQL, MongoDB

**Also** — Diffusers, TensorFlow, JavaScript, TypeScript, Git

---

## Research

**5 peer-reviewed papers · 75 citations · h-index 5** — [Scholar](https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en) · [ORCID](https://orcid.org/0009-0005-2420-6585) · [ResearchGate](https://www.researchgate.net/profile/Arifuzzaman-Joy)

| Paper | Venue | Year |
|---|---|:---:|
| [ML-assisted revelation of the best-performing single heterojunction thermophotovoltaic cell](https://doi.org/10.1016/j.seta.2025.104264) | *Sustainable Energy Technologies & Assessments* (Elsevier), Q1 | 2025 |
| [ML-enabled performance exploration of AuCuSe₄ in a thermophotovoltaic cell](https://doi.org/10.1016/j.solener.2024.112870) | *Solar Energy* (Elsevier), Q1 | 2024 |
| [Numerical studies on a ternary AgInTe₂ chalcopyrite thin-film solar cell](https://doi.org/10.1016/j.heliyon.2023.e19011) **· first author** | *Heliyon* (Cell Press), Q1 | 2023 |
| [Numerical prediction of PV performance of a CZTS-based thin-film solar cell](https://doi.org/10.1002/nano.202200228) | *Nano Select* (Wiley), Q2 | 2023 |
| [Open-source transformers in medical imaging](https://doi.org/10.14569/IJACSA.2024.01507126) — brain MRI, 99.60% accuracy, 0.90 Dice | *IJACSA* | 2024 |

<sub>Quartiles follow the latest JCR/Scopus release and vary by database and subject category.</sub>

**B.Sc. Electrical & Electronic Engineering**, University of Rajshahi (AI & Solar Energy Laboratory). SQL Advanced and REST API Intermediate (HackerRank), Deep Learning with TensorFlow (IBM), Prompt Engineering (Vanderbilt).

---

<div align="center">

### Got a model that needs to go live?

Send the model, your latency target, and the budget.
You'll get a straight answer about what it takes, including when the answer is that you don't need me.

<a href="https://www.upwork.com/freelancers/arifuzzamanj2"><img src="https://img.shields.io/badge/Hire%20me%20on%20Upwork-6FDA44?style=for-the-badge&logo=upwork&logoColor=white" alt="Upwork"></a>
<a href="mailto:joy.apee@gmail.com"><img src="https://img.shields.io/badge/joy.apee%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>

</div>
