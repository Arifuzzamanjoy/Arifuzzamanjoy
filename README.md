<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&duration=3200&pause=900&color=58A6FF&center=true&vCenter=true&width=760&height=80&lines=Hi%2C+I'm+Arifuzzaman+Joy+%F0%9F%91%8B;LLM+%26+AI+Agent+Infrastructure+Engineer;RAG+%E2%80%A2+GPU+Deploy+%E2%80%A2+MLOps;14+PRs+merged+into+a+4.6k-star+GPU+platform" alt="Arifuzzaman Joy" />

<p>
  <a href="https://www.upwork.com/freelancers/arifuzzamanj2"><img src="https://img.shields.io/badge/Hire%20me%20on%20Upwork-6FDA44?style=for-the-badge&logo=upwork&logoColor=white" alt="Upwork"></a>
  <a href="mailto:joy.apee@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://www.linkedin.com/in/arifuzzaman-joy-ru/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://arifuzzamanjoy.github.io/"><img src="https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio"></a>
</p>
<p>
  <a href="https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en"><img src="https://img.shields.io/badge/Scholar-4285F4?style=flat-square&logo=googlescholar&logoColor=white" alt="Google Scholar"></a>
  <a href="https://orcid.org/0009-0005-2420-6585"><img src="https://img.shields.io/badge/ORCID-A6CE39?style=flat-square&logo=orcid&logoColor=white" alt="ORCID"></a>
  <a href="https://huggingface.co/Joyapeee"><img src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black" alt="Hugging Face"></a>
  <img src="https://komarev.com/ghpvc/?username=Arifuzzamanjoy&color=0e75b6&style=flat-square&label=Profile+Views" alt="Profile Views">
</p>

</div>

---

## What I do

I get LLM and AI-agent systems running in production on serverless and rented GPUs, for a fraction of what the managed APIs cost.

Most of my work sits in the unglamorous layer: the Dockerfile that actually builds, the installer that survives a Vast.ai box with the wrong driver, the health check that stops silently dropping services. I also do research (5 peer-reviewed papers, 75 citations), so I'm comfortable reading a paper on Monday and having it deployed by Friday.

**What I'm usually hired for:**

- **Serverless GPU deployment** on RunPod, Modal, and Vast.ai. Dockerized endpoints, CI/CD, autoscaling that idles at near-zero cost.
- **Multi-agent systems**, including latent-space collaboration where agents pass hidden states instead of regenerating text.
- **RAG and document intelligence**: retrieval, citation tracking, multi-hop reasoning, and LLM-as-judge evaluation so you can actually tell if it got better.
- **Dynamic LoRA serving**: hot-swappable, domain-routed adapters on one base model. I train the adapters too.
- **Rescuing deployments that almost work**: multi-GPU OOM, driver mismatches, topology-aware placement, low-VRAM inference.

> Tell me your model and your latency or cost target, and I'll come back with a concrete plan and a number.

---

## Open-source work you can verify

[**Osmantic/ODS**](https://github.com/Osmantic/ODS) (4.6k ⭐) turns a PC into a self-hosted AI server — LLM inference, RAG, agents, image generation. I've opened [**23 PRs there, 14 merged**](https://github.com/Osmantic/ODS/pulls?q=is%3Apr+author%3AArifuzzamanjoy) across its schema, API, and deployment surface.

**Merged:**

- **Node diagnostics endpoint** ([#1664](https://github.com/Osmantic/ODS/pull/1664)) — `/api/node/capabilities`, runtime hardware and backend introspection
- **Schema hardening** — `gpu_backends` enum and validation ([#646](https://github.com/Osmantic/ODS/pull/646), [#675](https://github.com/Osmantic/ODS/pull/675)), compatibility blocks across 25 manifests ([#717](https://github.com/Osmantic/ODS/pull/717)), env-var defaults ([#716](https://github.com/Osmantic/ODS/pull/716), [#815](https://github.com/Osmantic/ODS/pull/815)), Dockerfile version pinning ([#816](https://github.com/Osmantic/ODS/pull/816))
- **CI compatibility** — Draft7Validator migration for jsonschema 3.x ([#817](https://github.com/Osmantic/ODS/pull/817))

**In review:**

- **p2p-GPU installer toolkit for Vast.ai** ([#983](https://github.com/Osmantic/ODS/pull/983)) — hardened multi-phase Bash, GPU-tier detection, ~28 documented host-environment failure modes
- **Non-HTTP health checks** ([#1343](https://github.com/Osmantic/ODS/pull/1343)) — `health_type: http|tcp|none` across schema, catalog generator, dashboard API, and shell scripts, fixing services that were being silently dropped
- **GPU idle telemetry** ([#1663](https://github.com/Osmantic/ODS/pull/1663)) and **mesh mode groundwork** ([#2120](https://github.com/Osmantic/ODS/pull/2120))

Also merged upstream into [**casys-kaist/LLMServingSim**](https://github.com/casys-kaist/LLMServingSim/pull/59) (370 ⭐, KAIST research lab): an RTX 4090 profile bundle with validation for Llama-3.1-8B. Open PRs at [kvcache-ai/ktransformers](https://github.com/kvcache-ai/ktransformers/pulls?q=is%3Apr+author%3AArifuzzamanjoy) (19k ⭐) and [theam/facility](https://github.com/theam/facility/pull/197).

---

## Featured: LatentMAS-SLoRA

<table>
<tr>
<td width="64%" valign="top">

### [LatentMAS-SLoRA](https://github.com/Arifuzzamanjoy/latent_mas_slora)

Picked up as [community extension #5 in Gen-Verse/LatentMAS](https://github.com/Gen-Verse/LatentMAS#-5-latentmas-slora), the official repo for the ICML 2026 **Spotlight** paper *Latent Collaboration in Multi-Agent Systems* ([arXiv:2511.20639](https://arxiv.org/abs/2511.20639)) — listed next to extensions from MIT's LAMM group.

It extends LatentMAS with role-specialized LoRA adapters that swap at runtime, plus latent-space collaboration where agents talk through hidden states instead of generated text. Ships with VLM support (Qwen2.5-VL-7B), RAG integration, and a RunPod serverless deployment with CI/CD.

**Pipeline:** Planner → Critic (latent) → Refiner (latent) → Judger. Critic and Refiner never generate text, roughly 200ms each.

**On scope:** the README spells out what's actually implemented via PEFT (dynamic loading, hot-swapping, weighted merging, LRU eviction) and what isn't there compared to real S-LoRA (no custom CUDA paging kernels, no heterogeneous batching). Benchmarks against vLLM S-LoRA are on the roadmap. I'd rather you find that in the README than in a demo call.

<p>
  <a href="https://github.com/Arifuzzamanjoy/latent_mas_slora"><img src="https://img.shields.io/badge/Code-181717?logo=github&logoColor=white" alt="GitHub"></a>
  <a href="https://www.youtube.com/watch?v=g7sxYjwgRRk"><img src="https://img.shields.io/badge/Demo-FF0000?logo=youtube&logoColor=white" alt="Demo"></a>
  <a href="https://github.com/Gen-Verse/LatentMAS#-5-latentmas-slora"><img src="https://img.shields.io/badge/Featured%20in-LatentMAS-58A6FF?logo=github" alt="Featured"></a>
</p>

`Python` · `PyTorch` · `PEFT / LoRA` · `Qwen2.5-VL` · `RAG` · `RunPod` · `Docker` · `CI/CD`

</td>
<td width="36%" valign="top">

```text
 Planner → Critic   (latent)
        → Refiner  (latent)
        → Judger   (text)

 + Dynamic LoRA routing
 + Domain auto-detection
 + 4 specialized adapters
 + Latent-space messaging
```

</td>
</tr>
</table>

---

## Selected projects

<table>
<tr>
<td width="50%" valign="top">

### [LatentMAS-SLoRA](https://github.com/Arifuzzamanjoy/latent_mas_slora)
Multi-agent reasoning with dynamic LoRA routing and latent-space collaboration.
`PyTorch` `PEFT` `Qwen2.5-VL` `RAG` `RunPod`

</td>
<td width="50%" valign="top">

### [RAG Chatbot + LLM-as-Judge Eval](https://github.com/Arifuzzamanjoy/RAG_Chatbot_-_Evaluation_LLM_as_Judge)
Retrieval over URL/JSON/CSV docs with citation tracking and automated eval.
`Python` `RAG` `Embeddings` `Evals`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [GPU Broker MCP Server](https://github.com/Arifuzzamanjoy/gpu-broker-mcp)
Stateless MCP server that brokers GPU compute for agents. Discover, reserve, dispatch, poll — no SSH keys or provider APIs to manage.
`MCP` `Python` `Streamable HTTP`

</td>
<td width="50%" valign="top">

### [FLUX.2 klein Serverless Worker](https://github.com/Arifuzzamanjoy/flux2kleinserverless)
RunPod worker for FLUX.2 [klein] text-to-image and image-to-image. Autoscales to near-zero idle cost.
`RunPod` `Serverless` `Docker` `Flux`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [Multi-GPU Video Generation (Wan 2.2)](https://github.com/Arifuzzamanjoy/Wan2.2_multigpu_runpod_gpu_with_gradio_interface_for_selfhosting_UI)
Topology-aware multi-GPU pipeline with per-GPU VRAM capping to fix multi-GPU OOM, plus a self-host UI.
`torch.distributed` `FSDP` `Docker` `Gradio`

</td>
<td width="50%" valign="top">

### [Diffusion Serverless Ecosystem](https://github.com/Arifuzzamanjoy/image_diffusion_ecosystem_serverlesss)
End-to-end serverless inference for diffusion models, Dockerized with CI/CD.
`Serverless` `Docker` `CI/CD` `Diffusers`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### [WordPress Cloner](https://github.com/Arifuzzamanjoy/wordpress-cloner)
Async site cloner with an 8-signal WP detection engine, REST API extraction, and WXR export. Packaged with tests and CI.
`Python` `aiohttp` `Scraping`

</td>
<td width="50%" valign="top">

### [Whisper Serverless Worker](https://github.com/Arifuzzamanjoy/worker-whisper)
Speech-to-text as a scalable on-demand endpoint.
`Whisper` `RunPod` `Serverless`

</td>
</tr>
</table>

<details>
<summary><b>More: LoRA training, NLP fine-tuning, low-VRAM inference</b></summary>

<br>

| Project | What it does | Tech |
|---|---|---|
| [Flux LoRA Generation Studio](https://github.com/Arifuzzamanjoy/Flux.2-dev-gradio-ui-runpod-A40-48-vram--H200-vram-) | Self-hosted Flux LoRA platform, A40 (48 GB) through H200, 4-bit quantization and batch inference | `Flux` `LoRA` `CUDA` |
| [Self-Hosted AI Starter Kit](https://github.com/Arifuzzamanjoy/self-hosted-ai-starter-kit-low_cost_cloud_cpu_with_external_share-) | Low-cost CPU-friendly self-hosting kit with secure external sharing | `Docker` `n8n` |
| [bangladeshi-tts-finetuning](https://github.com/Arifuzzamanjoy/bangladeshi-tts-finetuning) | Fine-tuning TTS for Bangla speech | `TTS` `Fine-tuning` |
| [bangla-punctuation-restoration](https://github.com/Arifuzzamanjoy/bangla-punctuation-restoration) | Transformer-based punctuation restoration for Bangla | `NLP` `Transformers` |
| [time-series forecasting](https://github.com/Arifuzzamanjoy/time-_series_forcasting_state-_of-_the_art) | Modern time-series forecasting models | `PyTorch` `Forecasting` |
| [Wan2GP](https://github.com/Arifuzzamanjoy/Wan2GP) | Low-VRAM video generation for consumer GPUs | `PyTorch` `Gradio` |
| [Ltx-Image-to-Video](https://github.com/Arifuzzamanjoy/Ltx-Image-to-Video-GradioInterface) | Image-to-video generation with a Gradio interface | `LTX` `Gradio` |

</details>

---

## Stack

**LLM / Agent infra**
<p>
<img src="https://img.shields.io/badge/RunPod-673AB7?style=flat-square&logo=runpod&logoColor=white">
<img src="https://img.shields.io/badge/Modal-7B68EE?style=flat-square">
<img src="https://img.shields.io/badge/Vast.ai-1f6feb?style=flat-square">
<img src="https://img.shields.io/badge/vLLM-FF6F00?style=flat-square">
<img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white">
<img src="https://img.shields.io/badge/MCP-000000?style=flat-square">
<img src="https://img.shields.io/badge/PEFT%2FLoRA-EE4C2C?style=flat-square">
<img src="https://img.shields.io/badge/RAG-4285F4?style=flat-square">
</p>

**ML / DL**
<p>
<img src="https://img.shields.io/badge/PyTorch-EE4C2C?style=flat-square&logo=pytorch&logoColor=white">
<img src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=flat-square&logo=huggingface&logoColor=black">
<img src="https://img.shields.io/badge/Transformers-FF9D00?style=flat-square">
<img src="https://img.shields.io/badge/Diffusers-FF4081?style=flat-square">
<img src="https://img.shields.io/badge/FSDP-DC382D?style=flat-square">
<img src="https://img.shields.io/badge/TensorFlow-FF6F00?style=flat-square&logo=tensorflow&logoColor=white">
</p>

**MLOps / infra**
<p>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white">
<img src="https://img.shields.io/badge/Docker%20Compose-2496ED?style=flat-square&logo=docker&logoColor=white">
<img src="https://img.shields.io/badge/CI%2FCD-2088FF?style=flat-square&logo=githubactions&logoColor=white">
<img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white">
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white">
<img src="https://img.shields.io/badge/pytest-0A9EDC?style=flat-square&logo=pytest&logoColor=white">
</p>

**Languages & data**
<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/SQL-336791?style=flat-square&logo=postgresql&logoColor=white">
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black">
<img src="https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white">
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white">
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white">
</p>

---

## Research

**5 peer-reviewed papers · 75 citations · h-index 5** — [Google Scholar](https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en) · [ORCID](https://orcid.org/0009-0005-2420-6585) · [ResearchGate](https://www.researchgate.net/profile/Arifuzzaman-Joy)

| Paper | Venue | Year | Link |
|---|---|:---:|---|
| Machine-learning-assisted revelation of the best-performing single heterojunction thermophotovoltaic cell | *Sustainable Energy Technologies & Assessments* (Elsevier) · Q1 | 2025 | [DOI](https://doi.org/10.1016/j.seta.2025.104264) · [arXiv](https://arxiv.org/abs/2408.01707) |
| Machine-learning-enabled performance exploration of AuCuSe₄ in a thermophotovoltaic cell | *Solar Energy* (Elsevier) · Q1 | 2024 | [DOI](https://doi.org/10.1016/j.solener.2024.112870) |
| Numerical studies on a ternary AgInTe₂ chalcopyrite thin-film solar cell **(first author)** | *Heliyon* (Cell Press) · Q1 | 2023 | [DOI](https://doi.org/10.1016/j.heliyon.2023.e19011) |
| Numerical prediction of the photovoltaic performance of a CZTS-based thin-film solar cell | *Nano Select* (Wiley) · Q2 | 2023 | [DOI](https://doi.org/10.1002/nano.202200228) |
| Unleashing the power of open-source transformers in medical imaging — brain MRI, 99.60% accuracy, 0.90 Dice | *IJACSA* | 2024 | [DOI](https://doi.org/10.14569/IJACSA.2024.01507126) |

Ongoing work on speech enhancement: [bone-conducted speech with neural networks](https://github.com/Arifuzzamanjoy/Bone-Conducted-Speech-Enhancement-With-Neural-Network) and [BoneGAN](https://github.com/Arifuzzamanjoy/BoneGAN-Generative-Adversarial-Networks-for-Bone-Conducted-Speech), evaluated with SNR, PESQ, and MOS.

<sub>Journal quartiles follow the most recent JCR/Scopus release and vary by database and subject category.</sub>

---

## Background

- **B.Sc. Electrical & Electronic Engineering**, University of Rajshahi, Bangladesh (Solar Energy Laboratory)
- SQL Advanced and REST API Intermediate (HackerRank) · Deep Learning with TensorFlow (IBM) · Prompt Engineering (Vanderbilt)

<div align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Arifuzzamanjoy&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58a6ff&icon_color=58a6ff&text_color=c9d1d9&count_private=true&cache_seconds=86400" alt="GitHub Stats">
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Arifuzzamanjoy&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9&langs_count=8&cache_seconds=86400" alt="Top Languages">
</div>

---

<div align="center">

### Got a model that needs to go live?

Send me the model, the target latency, and the budget. I'll tell you what it takes.

<a href="https://www.upwork.com/freelancers/arifuzzamanj2"><img src="https://img.shields.io/badge/Hire%20me%20on%20Upwork-6FDA44?style=for-the-badge&logo=upwork&logoColor=white" alt="Upwork"></a>
<a href="mailto:joy.apee@gmail.com"><img src="https://img.shields.io/badge/joy.apee%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
<a href="https://www.linkedin.com/in/arifuzzaman-joy-ru/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>

</div>
