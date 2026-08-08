<!-- ═══════════════════════════════════════════════════════════════════ -->
<!--              ARIFUZZAMAN JOY · GITHUB PROFILE README                 -->
<!--  Positioning: LLM & AI Agent Infrastructure Engineer                -->
<!-- ═══════════════════════════════════════════════════════════════════ -->

<div align="center">

<img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=600&size=26&duration=3200&pause=900&color=58A6FF&center=true&vCenter=true&width=720&height=80&lines=Hi%2C+I'm+Arifuzzaman+Joy+%F0%9F%91%8B;LLM+%26+AI+Agent+Infrastructure+Engineer;RAG+%E2%80%A2+GPU+Deploy+%E2%80%A2+MLOps;Published+ML+Researcher+%7C+7+papers%2C+3+in+Q1" alt="Arifuzzaman Joy" />

<p>
  <a href="mailto:joy.apee@gmail.com"><img src="https://img.shields.io/badge/Email-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"></a>
  <a href="https://www.linkedin.com/in/arifuzzaman-joy-ru/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"></a>
  <a href="https://arifuzzamanjoy.github.io/"><img src="https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=googlechrome&logoColor=white" alt="Portfolio"></a>
  <a href="https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en"><img src="https://img.shields.io/badge/Scholar-4285F4?style=for-the-badge&logo=googlescholar&logoColor=white" alt="Google Scholar"></a>
  <a href="https://orcid.org/0009-0005-2420-6585"><img src="https://img.shields.io/badge/ORCID-A6CE39?style=for-the-badge&logo=orcid&logoColor=white" alt="ORCID"></a>
  <a href="https://huggingface.co/Joyapeee"><img src="https://img.shields.io/badge/Hugging%20Face-FFD21E?style=for-the-badge&logo=huggingface&logoColor=black" alt="Hugging Face"></a>
  <img src="https://komarev.com/ghpvc/?username=Arifuzzamanjoy&color=0e75b6&style=for-the-badge&label=Profile+Views" alt="Profile Views">
</p>

</div>

---

## 🛠️ What I Build

I build the **infrastructure layer that makes LLM and AI-agent systems run in production**, reliably, on serverless and decentralized GPUs, at a fraction of managed-API cost. Published ML researcher (7 peer-reviewed papers, 3 in Q1 journals) who ships the hard part: multi-agent orchestration, RAG, and GPU deployment, not just notebooks.

- 🚀 **Production LLM / agent deployment** on RunPod, Modal, and Vast.ai. Dockerized serverless endpoints with CI/CD, plus self-contained installers that survive real GPU-provider failures (driver mismatches, multi-GPU OOM, topology-aware placement)
- 🧠 **Multi-agent systems with latent-space collaboration**, where agents exchange hidden states instead of generated text, cutting tokens and inference time *(open-sourced as LatentMAS-SLoRA)*
- 📚 **RAG / document intelligence**: embedding retrieval, citation tracking, multi-hop reasoning, and LLM-as-judge evaluation
- 🎛️ **Dynamic LoRA serving**: hot-swappable, domain-routed PEFT adapters on a single base model, with custom LoRA training built in
- 💸 **Inference cost optimization** through serverless autoscaling with near-zero idle cost

> 📨 *Tell me your model and your latency or cost target, and I'll reply with a concrete plan.*

---

## ⚡ Highlight: Production Open-Source GPU Infrastructure

<table>
<tr><td>

**[Osmantic / ODS](https://github.com/Osmantic/ODS)** (4,000+ ⭐) is a production, self-hostable AI-deployment platform for local and decentralized GPUs.
I've opened **[23 PRs, 14 merged upstream](https://github.com/Osmantic/ODS/pulls?q=is%3Apr+author%3AArifuzzamanjoy)** across the platform's schema, API, and deployment surface.

**Merged into main:**
- 🩺 **Node diagnostics endpoint** ([#1664](https://github.com/Osmantic/ODS/pull/1664)): `/api/node/capabilities` for runtime hardware and backend introspection
- 🔐 **Schema and security hardening**: `gpu_backends` enum and validation ([#646](https://github.com/Osmantic/ODS/pull/646), [#675](https://github.com/Osmantic/ODS/pull/675)), compatibility blocks across 25 manifests ([#717](https://github.com/Osmantic/ODS/pull/717)), env-var defaults ([#716](https://github.com/Osmantic/ODS/pull/716), [#815](https://github.com/Osmantic/ODS/pull/815)), and Dockerfile version pinning ([#816](https://github.com/Osmantic/ODS/pull/816))
- 🧪 **CI compatibility**: Draft7Validator migration for jsonschema 3.x ([#817](https://github.com/Osmantic/ODS/pull/817))

**Open, in review:**
- 🧰 **p2p-GPU installer toolkit for Vast.ai** ([#983](https://github.com/Osmantic/ODS/pull/983)): multi-phase hardened Bash (`set -euo pipefail`, hard-fail ACLs), GPU-tier detection, and ~28 documented host-environment failure modes
- 🔌 **Non-HTTP health checks** ([#1343](https://github.com/Osmantic/ODS/pull/1343)): `health_type: http|tcp|none` across schema, catalog generator, dashboard API, and shell scripts, fixing silently-dropped TCP/CLI services
- 📊 **GPU idle telemetry** ([#1663](https://github.com/Osmantic/ODS/pull/1663)) and **mesh mode groundwork** ([#2120](https://github.com/Osmantic/ODS/pull/2120))

*Stack: Bash installer hardening · Docker Compose · GPU tier detection · FastAPI · pytest · ShellCheck · Vast.ai quirks*

</td></tr>
</table>

---

## 🏆 Featured Project: LatentMAS-SLoRA

<table>
<tr>
<td width="64%" valign="top">

### 🧩 [LatentMAS-SLoRA](https://github.com/Arifuzzamanjoy/latent_mas_slora)

**Featured as community extension #5 in [Gen-Verse / LatentMAS](https://github.com/Gen-Verse/LatentMAS#-5-latentmas-slora)**, the official repo for the ICML 2026 **Spotlight** paper *Latent Collaboration in Multi-Agent Systems* ([arXiv:2511.20639](https://arxiv.org/abs/2511.20639)). Listed alongside extensions from MIT's LAMM group.

A multi-agent reasoning framework that augments LatentMAS with **role-specialized, dynamically switchable LoRA adapters** and **latent-space collaboration**, where agents communicate through hidden states rather than generated text. Includes VLM support (Qwen2.5-VL-7B), RAG integration, and RunPod serverless deployment with CI/CD.

**Pipeline:** Planner → Critic (latent) → Refiner (latent) → Judger, with the Critic and Refiner operating purely in hidden-state space at ~200ms each.

**On honesty about scope:** the repo documents exactly what it implements via PEFT (dynamic loading, hot-swapping, weighted merging, LRU eviction) and what it does *not* have versus true S-LoRA (no custom CUDA paging kernels, no heterogeneous batching). Benchmarks against vLLM S-LoRA are on the roadmap, not claimed as done.

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

## 🧰 Tech Stack

**LLM / Agent Infra**
<p>
<img src="https://img.shields.io/badge/RunPod-673AB7?style=flat-square&logo=runpod&logoColor=white">
<img src="https://img.shields.io/badge/Modal-7B68EE?style=flat-square">
<img src="https://img.shields.io/badge/Vast.ai-1f6feb?style=flat-square">
<img src="https://img.shields.io/badge/vLLM-FF6F00?style=flat-square">
<img src="https://img.shields.io/badge/LangChain-1C3C3C?style=flat-square&logo=langchain&logoColor=white">
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

**MLOps / Infra**
<p>
<img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white">
<img src="https://img.shields.io/badge/Docker%20Compose-2496ED?style=flat-square&logo=docker&logoColor=white">
<img src="https://img.shields.io/badge/CI%2FCD-2088FF?style=flat-square&logo=githubactions&logoColor=white">
<img src="https://img.shields.io/badge/Bash-4EAA25?style=flat-square&logo=gnubash&logoColor=white">
<img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white">
</p>
<!-- REMOVED: Kubernetes + AWS badges. Re-add only if you can point to a public repo that uses them.
     Every other badge here maps to a visible artifact; these two didn't. -->

**Languages & Data**
<p>
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white">
<img src="https://img.shields.io/badge/SQL-336791?style=flat-square&logo=postgresql&logoColor=white">
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black">
<img src="https://img.shields.io/badge/MongoDB-47A248?style=flat-square&logo=mongodb&logoColor=white">
<img src="https://img.shields.io/badge/Git-F05032?style=flat-square&logo=git&logoColor=white">
</p>

---

## 📌 Selected Projects

<table>
<tr>
<td width="50%" valign="top">

### 🤖 [LatentMAS-SLoRA](https://github.com/Arifuzzamanjoy/latent_mas_slora)
Multi-agent reasoning with dynamic LoRA routing and latent-space collaboration. Featured in Gen-Verse/LatentMAS.
`PyTorch` `PEFT` `Qwen2.5-VL` `RAG` `RunPod`

</td>
<td width="50%" valign="top">

### 📚 [RAG Chatbot + LLM-as-Judge Eval](https://github.com/Arifuzzamanjoy/RAG_Chatbot_-_Evaluation_LLM_as_Judge)
Retrieval pipeline over URL/JSON/CSV docs with citation tracking and automated LLM-as-judge evaluation.
`Python` `RAG` `Embeddings` `Evals`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### ⚡ [FLUX.2 klein Serverless Worker](https://github.com/Arifuzzamanjoy/flux2kleinserverless)
Serverless RunPod worker for FLUX.2 [klein] text-to-image and image-to-image, autoscaled with near-zero idle cost.
`RunPod` `Serverless` `Docker` `Flux`

</td>
<td width="50%" valign="top">

### 🧱 [Diffusion Serverless Ecosystem](https://github.com/Arifuzzamanjoy/image_diffusion_ecosystem_serverlesss)
End-to-end serverless inference ecosystem for diffusion models with Dockerized endpoints and CI/CD.
`Serverless` `Docker` `CI/CD` `Diffusers`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🎛️ [Multi-GPU Video Generation (Wan 2.2)](https://github.com/Arifuzzamanjoy/Wan2.2_multigpu_runpod_gpu_with_gradio_interface_for_selfhosting_UI)
Topology-aware multi-GPU pipeline with per-GPU VRAM capping (multi-GPU OOM fix) and self-host UI.
`torch.distributed` `FSDP` `Docker` `Gradio`

</td>
<td width="50%" valign="top">

### 🖼️ [Flux LoRA Generation Studio](https://github.com/Arifuzzamanjoy/Flux.2-dev-gradio-ui-runpod-A40-48-vram--H200-vram-)
Self-hosted Flux LoRA platform tuned for A40 (48 GB) through H200, with 4-bit quantization and batch inference.
`Flux` `LoRA` `CUDA` `Gradio`

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 🎙️ [Whisper Serverless Worker](https://github.com/Arifuzzamanjoy/worker-whisper)
Serverless speech-to-text worker, a scalable transcription endpoint on demand.
`Whisper` `RunPod` `Serverless`

</td>
<td width="50%" valign="top">

### 🏠 [Self-Hosted AI Starter Kit](https://github.com/Arifuzzamanjoy/self-hosted-ai-starter-kit-low_cost_cloud_cpu_with_external_share-)
Low-cost, CPU-friendly self-hosting kit for local AI tooling with secure external sharing.
`Docker` `n8n` `Self-Hosting`

</td>
</tr>
</table>

<details>
<summary><b>More projects: LoRA training, NLP fine-tuning, and low-VRAM inference</b></summary>

<br>

| Project | What it does | Tech |
|---|---|---|
| [Lora_Trainer_Imgen_Flux](https://github.com/Arifuzzamanjoy/Lora_Trainer_Imgen_Flux) | Custom LoRA training pipeline for Flux image models | `PEFT` `Flux` |
| [bangladeshi-tts-finetuning](https://github.com/Arifuzzamanjoy/bangladeshi-tts-finetuning) | Fine-tuning TTS for Bangla speech | `TTS` `Fine-tuning` |
| [bangla-punctuation-restoration](https://github.com/Arifuzzamanjoy/bangla-punctuation-restoration) | Transformer-based punctuation restoration for Bangla | `NLP` `Transformers` |
| [time-series forecasting](https://github.com/Arifuzzamanjoy/time-_series_forcasting_state-_of-_the_art) | Modern time-series forecasting models | `PyTorch` `Forecasting` |
| [Wan2GP](https://github.com/Arifuzzamanjoy/Wan2GP) | Low-VRAM video generation for consumer GPUs | `PyTorch` `Gradio` |
| [Ltx-Image-to-Video](https://github.com/Arifuzzamanjoy/Ltx-Image-to-Video-GradioInterface) | Image-to-video generation with a Gradio interface | `LTX` `Gradio` |

</details>

---

## 🔬 Research & Publications

> 7 peer-reviewed papers · 3 in Q1 journals · [Google Scholar](https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en) · [ORCID](https://orcid.org/0009-0005-2420-6585) · [ResearchGate](https://www.researchgate.net/profile/Arifuzzaman-Joy)

| # | Paper | Venue | Metrics | Year | Link |
|---|-------|-------|:---|:---:|------|
| 1 | Machine-learning-assisted revelation of the best-performing single heterojunction thermophotovoltaic cell | *Sustainable Energy Technologies & Assessments* (Elsevier) | JIF 7.4 · Q1 (Scopus) | 2025 | [DOI](https://doi.org/10.1016/j.seta.2025.104264) · [arXiv](https://arxiv.org/abs/2408.01707) |
| 2 | Machine-learning-enabled performance exploration of AuCuSe₄ in a thermophotovoltaic cell | *Solar Energy* (Elsevier) | JIF ~6.0 · Q1 | 2024 | [DOI](https://doi.org/10.1016/j.solener.2024.112870) |
| 3 | Numerical studies on a ternary AgInTe₂ chalcopyrite thin-film solar cell **(first author)** | *Heliyon* (Cell Press) | JIF ~3.5 · Q1 (Multidisciplinary) | 2023 | [DOI](https://doi.org/10.1016/j.heliyon.2023.e19011) |
| 4 | Numerical prediction of the photovoltaic performance of a CZTS-based thin-film solar cell | *Nano Select* (Wiley) | JIF 3.5 · Q2 · ESCI | 2023 | [DOI](https://doi.org/10.1002/nano.202200228) |
| 5 | Unleashing the power of open-source transformers in medical imaging (brain MRI: 99.60% classification accuracy, 0.90 Dice) | *IJACSA* | Peer-reviewed | 2024 | [DOI](https://doi.org/10.14569/IJACSA.2024.01507126) |
| 6 | Spectrum estimation for voiced speech using average weighted linear prediction | *[ ]* | — | 2024 | * * |
| 7 | Enhancement of bone-conducted speech using deep transfer learning | *[ ]* | — | 2024 | *[ ]* |

<sub>*Research themes: applied ML for materials and PV optimization, medical-imaging transformers, and speech enhancement. Journal metrics reflect the most recent JCR/Scopus release; quartile assignment varies by database and subject category.*</sub>

<!-- ACTION REQUIRED on rows 6 and 7: these currently have no venue and no DOI, and don't
     surface in literature search. Either fill in the venue + DOI, or relabel them as
     "preprint" / "under review" and drop the headline count to 5. Leaving them
     unsourced under a "peer-reviewed" heading is the single easiest thing for a
     grad-admissions reviewer to challenge. -->

---

## 📊 GitHub Analytics

<div align="center">
  <img height="165" src="https://github-readme-stats.vercel.app/api?username=Arifuzzamanjoy&show_icons=true&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58a6ff&icon_color=58a6ff&text_color=c9d1d9&count_private=true" alt="GitHub Stats">
  <img height="165" src="https://github-readme-stats.vercel.app/api/top-langs/?username=Arifuzzamanjoy&layout=compact&theme=tokyonight&hide_border=true&bg_color=0d1117&title_color=58a6ff&text_color=c9d1d9&langs_count=8" alt="Top Languages">
</div>

---

## 🎓 Education & Certifications

- 🎓 **B.Sc. Electrical & Electronic Engineering**, University of Rajshahi, Bangladesh (Solar Energy Laboratory)
- 🏅 SQL Advanced and REST API Intermediate (HackerRank) · Deep Learning with TensorFlow (IBM) · Prompt Engineering (Vanderbilt)

---

<div align="center">

### 💬 Let's build your inference layer

<a href="mailto:joy.apee@gmail.com"><img src="https://img.shields.io/badge/Email-joy.apee%40gmail.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white"></a>
<a href="https://www.linkedin.com/in/arifuzzaman-joy-ru/"><img src="https://img.shields.io/badge/Connect%20on%20LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"></a>

</div>
