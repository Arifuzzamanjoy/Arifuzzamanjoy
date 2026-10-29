<div align="center">

# Arifuzzaman Joy

**I put LLM and AI-agent systems into production on serverless and rented GPUs, for a fraction of what managed APIs cost.**

Upwork Top Rated · 100% Job Success

<a href="https://www.upwork.com/freelancers/arifuzzamanj2"><img src="https://img.shields.io/badge/Available%20on%20Upwork-6FDA44?style=for-the-badge&logo=upwork&logoColor=white" alt="Upwork"></a>

[Email](mailto:joy.apee@gmail.com) · [LinkedIn](https://www.linkedin.com/in/arifuzzaman-joy-ru/) · [Portfolio](https://arifuzzamanjoy.github.io/)

[Scholar](https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en) · [Hugging Face](https://huggingface.co/Joyapeee) · [ORCID](https://orcid.org/0009-0005-2420-6585)

</div>

---

## vLLM-Omni (7.1k stars)

My main open-source focus: keeping voice-cloning TTS correct under concurrency.

- **Found** [#8235](https://github.com/vllm-project/vllm-omni/issues/8235): CosyVoice3 returned 11.7 to 25% wrong voices at concurrency 8 (fixed in [#8224](https://github.com/vllm-project/vllm-omni/pull/8224)).
- **Merged** [#8456](https://github.com/vllm-project/vllm-omni/pull/8456): the benchmark now takes multiple reference voices, so mixed-voice batches can expose cross-request leaks.
- **CI check:** [#8555](https://github.com/vllm-project/vllm-omni/issues/8555) adds a nightly cross-request voice check for voice-cloning TTS, built on #8456. The missing piece is verifying who is actually speaking, which my speaker-embedding verifier (`cv3_verify`) does.
- **Cited** in the [Q4 roadmap discussion](https://github.com/vllm-project/vllm-omni/issues/8264#issuecomment-6143181659) as the basis for that nightly check.
- **Merged** [#6783](https://github.com/vllm-project/vllm-omni/pull/6783): engine args leaked between pipeline stages. One-line fix, 145 lines of tests.

---

## Also merged

- [**Osmantic/ODS**](https://github.com/Osmantic/ODS/pulls?q=is%3Apr+author%3AArifuzzamanjoy): 14 PRs, including [health checks for non-HTTP services](https://github.com/Osmantic/ODS/pull/1343)
- [**casys-kaist/LLMServingSim**](https://github.com/casys-kaist/LLMServingSim/pull/59): my profiling run exposed a KV-cache bug; after the fix, validation error fell from 87% to under 1%
- [**aimclub/OSA**](https://github.com/aimclub/OSA) (2 PRs) and [**neka-nat/freecad-mcp**](https://github.com/neka-nat/freecad-mcp/pull/149)

---

## What people hire me for

- Serverless GPU endpoints on RunPod, Modal, Vast.ai
- RAG pipelines with LLM-as-judge evals
- Multi-agent systems and hot-swappable LoRA adapters
- Rescuing deployments that almost work: OOM, driver mismatch, models that barely fit

---

## Selected work

**[LatentMAS-SLoRA](https://github.com/Arifuzzamanjoy/latent_mas_slora)**

Extends [LatentMAS](https://arxiv.org/abs/2511.20639) (Princeton, UIUC, Stanford; ICML 2026 Spotlight). Listed as [community extension #5](https://github.com/Gen-Verse/LatentMAS#-5-latentmas-slora) in the official Gen-Verse repo.

Agents pass hidden states instead of text, with role LoRA adapters switched on one base model. In my GSM8K run (26 items): 83.7% fewer output tokens and 5.5x faster than the text-based pipeline, no significant accuracy difference. I also fixed a semantic router that was quietly deciding 199 of 200 routes: 51.3% to 96.2% accuracy on 450 labelled items. Limits are in the README: PEFT switching, not true S-LoRA, adapters not trained yet. [Demo.](https://www.youtube.com/watch?v=g7sxYjwgRRk)

**[Vast.ai installer](https://github.com/Osmantic/ODS/pull/983)**

Hardened setup with 28 documented host failure modes. Not merged, kept as reference.

---

## Projects

- [**gpu-broker-mcp**](https://github.com/Arifuzzamanjoy/gpu-broker-mcp): MCP server for agents to reserve and dispatch GPUs
- [**RAG + LLM-as-Judge**](https://github.com/Arifuzzamanjoy/RAG_Chatbot_-_Evaluation_LLM_as_Judge): retrieval with citations and evals
- [**Wan 2.2 Multi-GPU**](https://github.com/Arifuzzamanjoy/Wan2.2_multigpu_runpod_gpu_with_gradio_interface_for_selfhosting_UI): per-GPU VRAM capping
- [**FLUX.2 klein Worker**](https://github.com/Arifuzzamanjoy/flux2kleinserverless): serverless, near-zero idle cost
- [**wacrm**](https://github.com/Arifuzzamanjoy/wacrm): WhatsApp CRM for immigration consultancies

---

## Stack

**GPU:** RunPod, Modal, Vast.ai, vLLM, Docker, FSDP, 4-bit quantization

**LLM:** PyTorch, PEFT/LoRA, Unsloth, Axolotl, LangChain, MCP, RAG

**Ops:** Python, FastAPI, Bash, GitHub Actions, pytest, SQL

---

## Research

B.Sc. EEE, University of Rajshahi. **5 papers, 77 citations, h-index 5** on solar cells and medical imaging, in *Solar Energy*, *Heliyon* (first author), *Nano Select*, *Sustainable Energy Tech. & Assessments*, and *IJACSA*. [Full list](https://scholar.google.com/citations?user=MGxpI3sAAAAJ&hl=en)

I'm most interested in health, energy, education, and scientific tooling.

---

<div align="center">

### Got a model that needs to go live?

Send the model, latency target, and budget. You'll get a straight answer, including when you don't need me.

<a href="https://www.upwork.com/freelancers/arifuzzamanj2"><img src="https://img.shields.io/badge/Hire%20me%20on%20Upwork-6FDA44?style=for-the-badge&logo=upwork&logoColor=white" alt="Upwork"></a>

[joy.apee@gmail.com](mailto:joy.apee@gmail.com)

</div>
