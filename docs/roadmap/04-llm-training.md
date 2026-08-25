# LLM Training & Knowledge — Resource Inventory

**Field:** LLM Training and Knowledge (how LLMs work, how to train/fine-tune them, and the surrounding ML/deep-learning fundamentals)
**Purpose:** This is a resource-discovery catalog, not a tutorial. A future agent will use this inventory to build actual learning notebooks, docs, and hands-on exercises. Every entry includes a real URL, a one-line description, and free/paid status.

## How this document is organized

1. Foundational math/ML prerequisites (brief, pointer-only)
2. Best courses on transformers/LLMs specifically (university, MOOC, practitioner)
3. Free structured courses & learning paths
4. Paid courses worth calling out
5. Foundational papers & explainer blog posts
6. Books
7. Hands-on labs / notebooks / sandboxes
8. GitHub repos worth studying or cloning
9. Free compute / GPU resources
10. Forums & communities
11. YouTube channels & podcasts
12. Practice project ideas
13. Datasets & model hubs
14. Cheat sheets / quick references / glossaries
15. Suggested learning progression (beginner → intermediate → advanced)

---

## 1. Foundational ML / Deep-Learning Prerequisites (brief — LLMs are the focus)

Keep this section as pointers only; don't over-invest here before getting into transformers.

| Resource | Description | Cost |
|---|---|---|
| [3Blue1Brown — Neural Networks series](https://www.3blue1brown.com/lessons/neural-networks/) (playlist: [YouTube](https://www.youtube.com/watch?v=aircAruvnKk)) | Visual, intuitive series: "But what is a neural network?", gradient descent, backprop intuition, backprop calculus. Best possible starting point for intuition. | Free |
| [3Blue1Brown — Essence of Linear Algebra](https://www.youtube.com/watch?v=fNk_zzaMoSs&list=PLZHQObOWTQDPD3MizzM2xVFitgF8hE_ab) | Visual linear-algebra primer (vectors, matrices, eigenvectors) needed for attention math. | Free |
| [Mathematics for Machine Learning (Deisenroth, Faisal, Ong) — free PDF](https://mml-book.github.io/book/mml-book.pdf) (site: [mml-book.com](https://mml-book.com/)) | Full free textbook: linear algebra, analytic geometry, matrix decompositions, vector calculus, probability, continuous optimization. | Free |
| [StatQuest with Josh Starmer (YouTube)](https://www.youtube.com/@statquest) | Clear, short explainers of probability/stats/ML concepts (cross-entropy, gradient descent, regularization) used constantly in LLM papers. | Free |
| [Stanford CS229 — Machine Learning](https://cs229.stanford.edu/) | Classic ML fundamentals course (supervised learning, optimization, basic neural nets) — useful refresher before deep-learning-specific material. | Free (materials) |
| [Deep Learning (Goodfellow, Bengio, Courville) — free online book](https://www.deeplearningbook.org/) | The standard deep-learning textbook; read the linear algebra, probability, and MLP/optimization chapters as prerequisites for transformers. | Free |

---

## 2. Best Courses Covering Transformers/LLMs Specifically

### University courses with public materials

| Course | Institution | Description | Cost |
|---|---|---|---|
| [CS224N: NLP with Deep Learning](https://web.stanford.edu/class/cs224n/) — [slides](https://web.stanford.edu/class/cs224n/slides/), [lecture 8 transformers slides](https://web.stanford.edu/class/cs224n/slides_w25/cs224n-2025-lecture08-transformers.pdf), [YouTube playlist](https://www.youtube.com/playlist?list=PLoROMvodv4rOaMFbaqxPDoLWjDaRAdP9D) | Stanford | The flagship NLP+deep-learning course; now explicitly covers pretraining, post-training, fine-tuning LLMs, RAG, agents, evaluation. Full public slides/readings/assignments. | Free (materials); paid if taken for-credit via [Stanford Online](https://online.stanford.edu/courses/xcs224n-natural-language-processing-deep-learning) |
| [CS25: Transformers United](https://web.stanford.edu/class/cs25/) | Stanford | Seminar-style course entirely dedicated to Transformers, with guest lectures from major researchers; all lectures on YouTube. | Free |
| [CS324: Advances in Foundation Models](https://stanford-cs324.github.io/winter2022/) | Stanford | Advanced course on foundation models: capabilities, harms, data, training, scaling — direct precursor to modern LLM curricula. | Free (materials) |
| [CME295: Transformers & Large Language Models](https://cme295.stanford.edu/) | Stanford | Applied course specifically on transformer/LLM internals and applications, with public study guide. | Free (study guide) |
| [MIT 6.S191: Introduction to Deep Learning](https://introtodeeplearning.com/) — Lecture 2 "RNNs, Transformers, and Attention" ([2025 lecture](https://www.youtube.com/watch?v=GvezxUdLrEk)), [GitHub repo](https://github.com/MITDeepLearning/introtodeeplearning) | MIT | MIT's intro deep-learning bootcamp; open-sourced slides, labs, and videos, explicitly covering LLMs/genAI each year. | Free |
| [Large Language Models, Spring 2025 (ETH Zürich, Rycolab)](https://rycolab.io/classes/llm-s25/) | ETH Zürich | Full public course page/modules dedicated entirely to LLMs (architectures, training, alignment, evaluation). | Free (materials) |
| [Harvard SEAS — Large Language Models: From Transformer Basics to Agentic AI](https://sites.harvard.edu/harvard-seas-llm/) | Harvard | Structured program from transformer fundamentals through agentic AI; public course page. | Paid program (materials page free) |

### MOOC-style / practitioner courses

| Course | Description | Cost |
|---|---|---|
| [Hugging Face LLM Course](https://huggingface.co/learn/llm-course/en/chapter1/1) | Free, hands-on curriculum covering Transformers library, tokenizers, datasets, fine-tuning, RLHF-adjacent alignment (formerly the "NLP Course"). Extremely widely used. | Free |
| [Hugging Face smol-course](https://huggingface.co/learn/smol-course/en/unit0/1) | Free path from instruction tuning → SFT → preference alignment (DPO-style), with free certification. | Free |
| [fast.ai — Practical Deep Learning for Coders](https://course.fast.ai/) (Part 2: [From Deep Learning Foundations to Stable Diffusion](https://course.fast.ai/Lessons/part2.html)) | Jeremy Howard's applied deep-learning course; Part 2 builds models (including generative/attention-based) from scratch using only Python + PyTorch fundamentals. | Free |
| [Andrej Karpathy — Neural Networks: Zero to Hero](https://karpathy.ai/zero-to-hero.html) (GitHub: [karpathy/nn-zero-to-hero](https://github.com/karpathy/nn-zero-to-hero)) | Best-in-class, code-first path from backprop (micrograd) → language modeling (makemore) → **building GPT from scratch** → **building the GPT tokenizer**. The single most recommended LLM-specific course among practitioners. | Free |
| [Andrej Karpathy — "Let's reproduce GPT-2 (124M)"](https://www.youtube.com/watch?v=l8pRSuU81PU) | 4-hour deep dive reproducing GPT-2 end to end, continuing the Zero-to-Hero series into full pretraining. | Free |
| [DeepLearning.AI — Fine-tuning & RL for LLMs: Intro to Post-training](https://www.deeplearning.ai/courses/fine-tuning-and-reinforcement-learning-for-llms-intro-to-post-training) | Short course on post-training: fine-tuning + RL to shape behavior/reasoning/safety. | Free (short course) |
| [DeepLearning.AI — Finetuning Large Language Models](https://www.deeplearning.ai/courses/finetuning-large-language-models) | Practical short course on fine-tuning workflows for LLMs. | Free (short course) |
| [DeepLearning.AI — Reinforcement Learning From Human Feedback](https://www.deeplearning.ai/courses/reinforcement-learning-from-human-feedback) | Short course specifically walking through RLHF mechanics. | Free (short course) |
| [Coursera — Generative AI with Large Language Models (DeepLearning.AI + AWS)](https://www.coursera.org/learn/generative-ai-with-llms) | Broader survey course covering transformer architecture, pretraining, fine-tuning, PEFT/LoRA, and RLHF, with labs. | Free to audit; paid for certificate |
| [Full Stack Deep Learning](https://fullstackdeeplearning.com/) — [LLM Bootcamp materials](https://fullstackdeeplearning.com/course/2022/) | Production-oriented deep learning + LLM bootcamp: prompt engineering, LLMOps, experiment tracking (W&B labs), deployment. | Free (course materials/videos) |
| [Weights & Biases — free ML/LLM courses (wandb/edu)](https://github.com/wandb/edu) | W&B's own course repo, incl. "Training and Fine-tuning LLMs" and "Building LLM-Powered Apps," with experiment-tracking labs. | Free |

---

## 3. Free Courses & Structured Learning Paths (roundup)

- [Hugging Face LLM Course](https://huggingface.co/learn/llm-course/en/chapter1/1) — free, comprehensive, includes chapter on tokenizers built from scratch (BPE/WordPiece/Unigram).
- [Hugging Face smol-course](https://huggingface.co/learn/smol-course/en/unit0/1) — free, instruction-tuning → preference alignment, free cert.
- [Andrej Karpathy's Zero to Hero](https://karpathy.ai/zero-to-hero.html) — free, the best hands-on "build it yourself" path.
- [fast.ai Practical Deep Learning for Coders](https://course.fast.ai/) — free, applied, code-first.
- [MIT 6.S191](https://introtodeeplearning.com/) — free, lecture videos + labs, updated yearly.
- [rlhfbook.com](https://rlhfbook.com/) — free, continuously-updated online textbook/course on RLHF and post-training (see §6 Books and §5 Papers).
- [EleutherAI Cookbook](https://github.com/EleutherAI/cookbook) — free, practical guides/code for the math and systems side of training LLMs at scale.
- [DeepLearning.AI short courses catalog](https://www.deeplearning.ai/courses/) — free, filter for LLM/fine-tuning/RLHF titles.
- [Learn Prompting — LLM courses roundup](https://learnprompting.org/blog/large-language-models-courses) — free aggregator of many LLM courses, useful as a secondary discovery source.

---

## 4. Paid Courses Worth Calling Out (clearly labeled)

| Course | Description | Cost |
|---|---|---|
| [Coursera — Generative AI Advanced Fine-Tuning for LLMs](https://www.coursera.org/learn/generative-ai-advanced-fine-tuning-for-llms) | Covers RLHF, PPO, and DPO with cloud labs; certificate requires payment. | Paid (labs free, cert paid) |
| [Coursera — Introduction to LLMs and Hugging Face](https://www.coursera.org/learn/introduction-to-llms-huggingface) | Practical intro to fine-tuning/evaluating/deploying transformer models via the HF ecosystem. | Paid (audit free) |
| [Harvard SEAS — Large Language Models: From Transformer Basics to Agentic AI](https://sites.harvard.edu/harvard-seas-llm/) | 19 hours of live instruction, structured university-style program. | Paid |
| [Udemy — various LLM fine-tuning courses](https://www.udemy.com/topic/large-language-models/) (e.g. "LLM Fine-Tuning Mastery: Basic to Advanced + Cloud Deploy") | Practitioner-style video courses on fine-tuning workflows; quality varies, check reviews before buying. | Paid |
| [Nathan Lambert — RLHF Book (Manning print/liveBook edition)](https://www.manning.com/books/reinforcement-learning-from-human-feedback) | Print/ePub/liveBook edition of the RLHF book (the web version is free — see §6). | Paid (print); free (web) |
| [Weights & Biases — "Training and Fine-tuning LLMs" course](https://github.com/wandb/edu) | Some W&B courses are free; check individual course pages — listed here for completeness since some cohort/enterprise versions are paid. | Mostly free, verify per-course |

---

## 5. Foundational Papers & Explainer Blog Posts

### Core architecture

| Item | Description | Cost |
|---|---|---|
| [Attention Is All You Need (Vaswani et al., 2017)](https://arxiv.org/abs/1706.03762) | The original Transformer paper — self-attention, multi-head attention, positional encoding, encoder-decoder stack. | Free |
| [The Illustrated Transformer — Jay Alammar](https://jalammar.github.io/illustrated-transformer/) | The most widely referenced visual walkthrough of the Transformer architecture. | Free |
| [The Illustrated GPT-2 — Jay Alammar](https://jalammar.github.io/illustrated-gpt2/) | Visual explanation of GPT-2 as a decoder-only transformer, building on the transformer post. | Free |
| [Jay Alammar's blog index](https://jalammar.github.io/) | Additional illustrated posts (retrieval transformers, BERT, word2vec) — great supplementary reading. | Free |
| [Andrej Karpathy — "Let's build GPT: from scratch, in code, spelled out" (YouTube)](https://www.youtube.com/watch?v=kCc8FmEb1nY) | Code-along video building GPT from the ground up, paired with [ng-video-lecture GitHub](https://github.com/karpathy/ng-video-lecture). | Free |
| [Andrej Karpathy — "Let's build the GPT Tokenizer" (YouTube)](https://www.youtube.com/watch?v=zduSFxRajkE) | Deep dive on byte-level BPE tokenization and why tokenization causes many LLM quirks; code in [karpathy/minbpe](https://github.com/karpathy/minbpe). | Free |
| [Karpathy — "State of GPT" (Microsoft Build talk, YouTube)](https://www.youtube.com/watch?v=bZQun8Y4L2A) | High-level but technically grounded overview of the full GPT training pipeline (pretraining → SFT → RM → RLHF). | Free |

### Pretraining & scaling

| Item | Description | Cost |
|---|---|---|
| [BERT: Pre-training of Deep Bidirectional Transformers (Devlin et al., 2018)](https://arxiv.org/abs/1810.04805) | Introduced masked-LM pretraining + fine-tuning paradigm for bidirectional encoders. | Free |
| [Language Models are Unsupervised Multitask Learners — GPT-2 (Radford et al., 2019)](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf) | Large-scale autoregressive LM pretraining and zero-shot task transfer. | Free |
| [Language Models are Few-Shot Learners — GPT-3 (Brown et al., 2020)](https://arxiv.org/abs/2005.14165) | Showed scale enables strong few-shot/zero-shot performance without fine-tuning. | Free |
| [Scaling Laws for Neural Language Models (Kaplan et al., 2020)](https://arxiv.org/abs/2001.08361) | Established power-law relationships between loss, model size, data, and compute. | Free |
| [Training Compute-Optimal LLMs — "Chinchilla" (Hoffmann et al., 2022)](https://arxiv.org/abs/2203.15556) | Revised Kaplan's scaling laws — argues for far more training tokens relative to parameters. | Free |
| [EleutherAI — Transformer Math 101](https://blog.eleuther.ai/transformer-math/) | Practical blog post with the actual compute/memory formulas for training and serving transformers, incl. distributed-training memory breakdown. | Free |
| [EleutherAI Cookbook (GitHub)](https://github.com/EleutherAI/cookbook) | Companion code/notebooks for transformer-math and large-scale training practicalities. | Free |

### Instruction tuning, alignment, RLHF

| Item | Description | Cost |
|---|---|---|
| [Training Language Models to Follow Instructions with Human Feedback — InstructGPT (Ouyang et al., 2022)](https://arxiv.org/abs/2203.02155) | The canonical RLHF paper: SFT → reward model → PPO pipeline. | Free |
| [Finetuned Language Models Are Zero-Shot Learners — FLAN (Wei et al., 2021/2022)](https://arxiv.org/abs/2109.01652) | Introduced instruction tuning across many NLP tasks phrased as natural-language instructions. | Free |
| [The Flan Collection (Longpre et al., 2023)](https://arxiv.org/abs/2301.13688) | Studies instruction-tuning data/method design choices, incl. chain-of-thought mixing. | Free |
| [Direct Preference Optimization (Rafailov et al., 2023)](https://arxiv.org/abs/2305.18290) | DPO — reformulates RLHF as a simple classification-style loss on preference pairs, no explicit reward model or RL loop. | Free |
| [Hugging Face — "Preference Tuning LLMs" blog](https://huggingface.co/blog/pref-tuning) | Practical comparison of DPO and related preference-optimization methods. | Free |
| [OpenAI — "Instruction Following" blog announcement](https://openai.com/index/instruction-following/) | OpenAI's own summary of the InstructGPT work. | Free |
| [Chain-of-Thought Prompting Elicits Reasoning (Wei et al., 2022)](https://arxiv.org/abs/2201.11903) | Introduced CoT prompting; foundational for later reasoning/RL post-training work. | Free |

### Efficient fine-tuning (LoRA / QLoRA / PEFT)

| Item | Description | Cost |
|---|---|---|
| [LoRA: Low-Rank Adaptation of Large Language Models (Hu et al., 2021)](https://arxiv.org/abs/2106.09685) | Original LoRA paper — freezes base weights, injects trainable low-rank adapters. | Free |
| [QLoRA: Efficient Finetuning of Quantized LLMs (Dettmers et al., 2023)](https://arxiv.org/abs/2305.14314) | Combines 4-bit NF4 quantization + LoRA + paged optimizers; fine-tunes 65B models on one 48GB GPU. | Free |
| [Hugging Face — PEFT blog announcement](https://huggingface.co/blog/peft) | Overview of the PEFT library and the family of parameter-efficient methods it supports. | Free |
| [Sebastian Raschka — "Practical Tips for Finetuning LLMs Using LoRA"](https://magazine.sebastianraschka.com/p/practical-tips-for-finetuning-llms) | Empirical, practitioner-level tips on LoRA hyperparameters, rank choice, and pitfalls. | Free |

### Tokenization

| Item | Description | Cost |
|---|---|---|
| [Hugging Face LLM Course — Byte-Pair Encoding chapter](https://huggingface.co/learn/llm-course/en/chapter6/5) | Explains BPE training/encoding algorithm step by step with code. | Free |
| [Sebastian Raschka — "Byte Pair Encoding From Scratch"](https://sebastianraschka.com/blog/2025/bpe-from-scratch.html) | Implements BPE tokenizer training from scratch in Python. | Free |
| [Karpathy's minbpe (GitHub)](https://github.com/karpathy/minbpe) | Minimal, clean BPE tokenizer implementation, companion to the tokenizer video above. | Free |

### Quantization (for inference/deployment context)

| Item | Description | Cost |
|---|---|---|
| ["GGUF vs GPTQ vs AWQ" — plain-English guide](https://ai-tldr.dev/learn/local-open-models/quantization-and-formats/gguf-vs-gptq-vs-awq/) | Clear comparison of the model-file-format (GGUF) vs quantization-algorithm (GPTQ/AWQ) distinction. | Free |
| [Maarten Grootendorst — "Which Quantization Method is Right for You?"](https://newsletter.maartengrootendorst.com/p/which-quantization-method-is-right) | Well-illustrated newsletter post comparing quantization approaches for local LLM inference. | Free |

---

## 6. Books

| Book | Description | Cost |
|---|---|---|
| [Build a Large Language Model (From Scratch) — Sebastian Raschka](https://sebastianraschka.com/llms-from-scratch/) (companion code: [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch)) | Implements a GPT-style LLM end-to-end in PyTorch: embeddings, attention, architecture, pretraining, classification/instruction fine-tuning, loading pretrained weights. The single best hands-on companion book for this field. | Paid (book); free companion GitHub code |
| [RLHF Book — Nathan Lambert (rlhfbook.com)](https://rlhfbook.com/) (GitHub source: [natolambert/rlhf-book](https://github.com/natolambert/rlhf-book)) | Continuously-updated free textbook on RLHF and modern LLM post-training: instruction tuning, reward modeling, PPO, DPO/direct alignment, synthetic data, evaluation. | Free (web); paid (Manning print/ePub/liveBook edition) |
| [AI Engineering: Building Applications with Foundation Models — Chip Huyen (O'Reilly, 2025)](https://huyenchip.com/books/) | Practical book on the application layer around foundation models: prompting, RAG, fine-tuning, agents, dataset engineering, evaluation. Complements the from-scratch books with a systems/product view. | Paid |
| [Mathematics for Machine Learning — Deisenroth, Faisal, Ong (free PDF)](https://mml-book.github.io/book/mml-book.pdf) | Free official PDF math prerequisite text (see §1). | Free |
| [Deep Learning — Goodfellow, Bengio, Courville (free online)](https://www.deeplearningbook.org/) | Classic deep-learning textbook; useful for MLP/optimization/regularization background before transformers. | Free |
| [Speech and Language Processing — Jurafsky & Martin (draft chapters online)](https://web.stanford.edu/~jurafsky/slp3/) | Standard NLP textbook; current draft includes transformer, LLM, and RLHF-adjacent chapters, free online. | Free |

---

## 7. Hands-on Labs / Notebooks / Sandboxes

| Resource | Description | Cost |
|---|---|---|
| [Unsloth Notebooks](https://github.com/unslothai/notebooks) | 100+ ready-to-run Colab/Kaggle notebooks for fine-tuning popular open models (Llama, Qwen, Mistral, Gemma, Phi) with LoRA/QLoRA on free T4 GPUs. | Free |
| [poloclub/Fine-tuning-LLMs](https://github.com/poloclub/Fine-tuning-LLMs) | Step-by-step Colab tutorial fine-tuning Llama 2 with QLoRA on custom data, free-tier friendly. | Free |
| [ashishpatel26/LLM-Finetuning](https://github.com/ashishpatel26/LLM-Finetuning) — [example Colab notebook](https://colab.research.google.com/github/ashishpatel26/LLM-Finetuning/blob/main/2.Fine_Tune_Your_Own_Llama_2_Model_in_a_Colab_Notebook.ipynb) | Large collection of Colab notebooks for fine-tuning various LLMs. | Free |
| [Ak-Gautam/efficient_llm_fine_tunes](https://github.com/Ak-Gautam/efficient_llm_fine_tunes) | Colab-focused fine-tuning of small models (Qwen1.5-0.5B, Mistral 7B) explicitly designed for free T4 GPUs. | Free |
| [karpathy/nn-zero-to-hero](https://github.com/karpathy/nn-zero-to-hero) | All notebooks/code for the Zero-to-Hero series — micrograd, makemore, GPT-from-scratch, tokenizer — runnable locally or in Colab. | Free |
| [karpathy/nanoGPT](https://github.com/karpathy/nanoGPT) | The simplest repo for training/fine-tuning medium-sized GPTs; `train.py`/`model.py` are ~300 lines each — ideal hands-on pretraining sandbox. | Free |
| [karpathy/build-nanogpt](https://github.com/karpathy/build-nanogpt) | Companion repo to the "Let's reproduce GPT-2" video — step-by-step build with intermediate checkpoints. | Free |
| [Google Colab](https://colab.research.google.com/) | Free-tier notebook environment with T4 GPU access; the default sandbox for most fine-tuning tutorials above. | Free (Pro tiers paid) |
| [Kaggle Notebooks](https://www.kaggle.com/code) | Free notebook environment with free GPU/TPU quota (30h/week GPU) — good alternative to Colab, also hosts many LLM fine-tuning notebooks directly. | Free |
| [Hugging Face Spaces](https://huggingface.co/spaces) | Free hosting for Gradio/Streamlit demo apps; useful for deploying/sharing a fine-tuned model demo end-to-end. | Free tier + paid GPU Spaces |

---

## 8. GitHub Repos Worth Studying or Cloning

### Minimal / from-scratch implementations

| Repo | Description | Cost |
|---|---|---|
| [karpathy/minGPT](https://github.com/karpathy/mingpt) | Minimal (~300-line) PyTorch re-implementation of GPT — the cleanest place to read the actual model code. | Free |
| [karpathy/nanoGPT](https://github.com/karpathy/nanoGPT) | Practical rewrite of minGPT for actually training/fine-tuning GPTs efficiently. | Free |
| [karpathy/llm.c](https://github.com/karpathy/llm.c) | GPT-2/3 training in raw C/CUDA — for understanding LLM training at the systems/kernel level. | Free |
| [karpathy/minbpe](https://github.com/karpathy/minbpe) | Minimal byte-level BPE tokenizer implementation (companion to the tokenizer video). | Free |
| [rasbt/LLMs-from-scratch](https://github.com/rasbt/LLMs-from-scratch) | Full code companion to Raschka's book — GPT architecture, pretraining, fine-tuning, instruction tuning. | Free |
| [tanishqkumar/beyond-nanogpt](https://github.com/tanishqkumar/beyond-nanogpt) | Extends nanoGPT-style minimalism to more modern architecture variants and research ideas. | Free |
| [KellerJordan/modded-nanogpt](https://github.com/KellerJordan/modded-nanogpt) | Community speedrun project optimizing nanoGPT training speed — good for learning training-efficiency tricks. | Free |

### Fine-tuning frameworks / toolkits

| Repo | Description | Cost |
|---|---|---|
| [huggingface/peft](https://github.com/huggingface/peft) | Official parameter-efficient fine-tuning library (LoRA, prefix-tuning, prompt-tuning, etc.), integrates with Transformers/Accelerate. | Free |
| [huggingface/trl](https://github.com/huggingface/trl) | Hugging Face's library for SFT, reward modeling, PPO, DPO and other RLHF-style post-training methods. | Free |
| [huggingface/transformers](https://github.com/huggingface/transformers) | The core library implementing virtually every modern transformer architecture. | Free |
| [unslothai/unsloth](https://github.com/unslothai/unsloth) | Speed/VRAM-optimized fine-tuning kernels; ~2x faster, much lower memory single-GPU LoRA/QLoRA fine-tuning. | Free (open-source core; paid hosted options) |
| [OpenAccess-AI-Collective/axolotl](https://github.com/OpenAccess-AI-Collective/axolotl) | YAML-config-driven fine-tuning framework supporting many models/methods, multi-GPU/distributed training. | Free |
| [hiyouga/LLaMA-Factory](https://github.com/hiyouga/LlamaFactory) | Unified fine-tuning framework for 100+ models with CLI + web UI, optional Unsloth acceleration backend. | Free |
| [microsoft/DeepSpeed](https://github.com/microsoft/DeepSpeed) | Distributed training library (ZeRO optimizer stages) used to train/fine-tune very large models efficiently. | Free |
| [NVIDIA/Megatron-LM](https://github.com/NVIDIA/Megatron-LM) | Large-scale transformer training framework with tensor/pipeline parallelism — read for understanding real large-scale pretraining infra. | Free |
| [EleutherAI/gpt-neox](https://github.com/EleutherAI/gpt-neox) | EleutherAI's own large-scale GPU/TPU training codebase for GPT-style models, built on Megatron/DeepSpeed. | Free |

### Evaluation

| Repo | Description | Cost |
|---|---|---|
| [EleutherAI/lm-evaluation-harness](https://github.com/EleutherAI/lm-evaluation-harness) | The standard unified framework for benchmarking LLMs (MMLU, and hundreds of other tasks); backs the HF Open LLM Leaderboard. | Free |
| [stanford-crfm/helm](https://github.com/stanford-crfm/helm) | Stanford's Holistic Evaluation of Language Models — broad, multi-metric evaluation framework/alternative to lm-eval-harness. | Free |
| [openai/evals](https://github.com/openai/evals) | OpenAI's framework/registry for building and running LLM evaluations. | Free |

### Awesome-lists / dataset-prep tooling

| Repo | Description | Cost |
|---|---|---|
| [Hannibal046/Awesome-LLM](https://github.com/hannibal046/awesome-llm) | The main curated "awesome list" for LLMs — papers, open models, training/deployment tools, release timelines. | Free |
| [opendilab/awesome-RLHF](https://github.com/opendilab/awesome-RLHF) | Curated list of RLHF papers, code, and resources. | Free |
| [togethercomputer/RedPajama-Data](https://github.com/togethercomputer/RedPajama-Data) | Dataset-prep/data pipeline code for the RedPajama pretraining corpus (see §13). | Free |
| [huggingface/datatrove](https://github.com/huggingface/datatrove) | Hugging Face's large-scale data-processing library used to build FineWeb — good reference for dataset-prep pipelines. | Free |

---

## 9. Free Compute / GPU Resources

| Resource | Description | Cost |
|---|---|---|
| [Google Colab (free tier)](https://colab.research.google.com/) | Free T4 GPU notebooks; the default environment for almost all fine-tuning tutorials in this list. | Free |
| [Kaggle Notebooks](https://www.kaggle.com/code) | Free ~30 GPU-hours/week (P100/T4x2) plus TPU quota — good alternative/backup to Colab. | Free |
| [Google Cloud TPU Research Cloud (TRC)](https://sites.research.google/trc/about/) | Free TPU access program for researchers/students doing open research (application required). | Free (application-based) |
| [GitHub Student Developer Pack](https://education.github.com/pack) | Bundles multiple cloud-credit offers (Azure, DigitalOcean, etc.) for verified students. | Free (student-gated) |
| [AWS Educate](https://aws.amazon.com/education/awseducate/) | Cloud credits (~$100, renewable) for students at accredited institutions, incl. GPU EC2 instances. | Free (student-gated) |
| [Azure for Students](https://azure.microsoft.com/en-us/free/students/) | Free Azure credit for verified students, no credit card required. | Free (student-gated) |
| [Modal — Academics program](https://modal.com/pricing) | Up to $10,000 in compute credits for eligible academics/researchers (student ID or research affiliation required). | Free (application-based) |
| [Lambda / Google Cloud / Azure / Oracle new-account credits](https://cloud.google.com/free) | Standard new-account free credits (e.g. GCP $300, Azure $200, Oracle always-free GPU-adjacent tier) — useful for short bursts of larger-scale experimentation. | Free (time/credit-limited) |
| [Hugging Face Spaces (free GPU-tier hardware for demos)](https://huggingface.co/docs/hub/spaces-gpus) | Free CPU Spaces + paid GPU upgrade option for hosting/demoing fine-tuned models. | Free tier + paid upgrades |

---

## 10. Forums & Communities

| Community | Description | Cost |
|---|---|---|
| [r/LocalLLaMA (Reddit)](https://www.reddit.com/r/LocalLLaMA/) | The largest, most active community for local/open-weight LLMs — models, fine-tuning, hardware, benchmarks. | Free |
| [r/MachineLearning (Reddit)](https://www.reddit.com/r/MachineLearning/) | General ML research discussion subreddit, frequent paper discussions relevant to LLMs. | Free |
| [r/learnmachinelearning (Reddit)](https://www.reddit.com/r/learnmachinelearning/) | Beginner-friendly ML learning community; good for course reviews and study-plan discussions. | Free |
| [EleutherAI Discord](https://www.eleuther.ai/community) | Public Discord for the open research collective behind GPT-NeoX/Pythia and much LLM-training research; very active, technical. | Free |
| [Hugging Face Discord](https://huggingface.co/join/discord) | Official community server for Transformers/Diffusers/PEFT/TRL discussion and support. | Free |
| [Hugging Face Forums](https://discuss.huggingface.co/) | Official Q&A forum for the HF ecosystem (Transformers, PEFT, TRL, tokenizers, datasets). | Free |
| [PyTorch Forums](https://discuss.pytorch.org/) | Official PyTorch community forum — useful for training/implementation-level debugging. | Free |
| [Latent Space Discord (from the podcast/newsletter community)](https://www.latent.space/) | Practitioner-focused AI engineering community tied to the Latent Space podcast/newsletter. | Free |

---

## 11. YouTube Channels & Podcasts

### YouTube channels

| Channel | Description | Cost |
|---|---|---|
| [Andrej Karpathy (YouTube)](https://www.youtube.com/@AndrejKarpathy) | Build-it-from-scratch lectures: nanoGPT, tokenizers, "State of GPT," Zero-to-Hero series. The single best channel for this field. | Free |
| [Yannic Kilcher (YouTube)](https://www.youtube.com/@YannicKilcher) | In-depth paper walkthroughs of cutting-edge ML/LLM research, often line-by-line. | Free |
| [Two Minute Papers (YouTube)](https://www.youtube.com/@TwoMinutePapers) | Fast, accessible summaries of frontier AI/ML research papers. | Free |
| [StatQuest with Josh Starmer (YouTube)](https://www.youtube.com/@statquest) | Short, extremely clear explainers for the statistics/ML building blocks behind LLMs. | Free |
| [3Blue1Brown (YouTube)](https://www.youtube.com/@3blue1brown) | Visual math/neural-network intuition (see §1). | Free |
| [AI Explained (YouTube)](https://www.youtube.com/@ai-explained-) | Clear commentary/summaries of major AI/LLM releases and research news. | Free |

### Podcasts

| Podcast | Description | Cost |
|---|---|---|
| [Dwarkesh Podcast](https://www.dwarkesh.com/podcast) | Long-form, deeply researched interviews with frontier AI researchers and lab leaders. | Free |
| [Latent Space (podcast + newsletter)](https://www.latent.space/) | AI-engineer-focused technical interviews on models, agents, evals, infra — very LLM-practitioner-oriented. | Free |
| [No Priors](https://www.no-priors.com/) | AI startup/investing-angle podcast hosted by Sarah Guo and Elad Gil — useful for industry context around LLM development. | Free |
| [TWIML AI Podcast (This Week in Machine Learning & AI)](https://twimlai.com/podcast/twimlai/) | Long-running podcast interviewing ML researchers/engineers on technical topics including LLMs. | Free |

---

## 12. Practice Project Ideas

Ordered roughly from easiest to most advanced:

1. **Toy transformer from scratch** — train a character-level or token-level transformer (à la nanoGPT/makemore) on a tiny dataset (names, Shakespeare, arithmetic, copy/reverse tasks). Goal: understand embeddings, attention, loss curves, and generation mechanics before touching any framework.
2. **Build and test your own BPE tokenizer** — implement byte-level BPE (following Karpathy's minbpe or Raschka's from-scratch post) and compare vocab/merge behavior against `tiktoken`.
3. **Reproduce GPT-2 (124M) end-to-end** — follow Karpathy's "Let's reproduce GPT-2" video/repo on a free-tier or rented GPU; measure loss curves and compare to the paper.
4. **LoRA fine-tune a small open model** (e.g. TinyLlama, Qwen2.5-0.5B/1.5B, Gemma-2B) on a narrow instruction task (rewriting, style transfer, summarization) using Unsloth or PEFT on a free Colab/Kaggle T4 GPU. Evaluate base vs fine-tuned on a held-out set.
5. **QLoRA fine-tune a 7B model** on a single consumer/free-tier GPU using 4-bit quantization; compare VRAM usage and quality against full-precision LoRA.
6. **DPO / preference-alignment mini-project** — take a small SFT'd model and run DPO (via TRL) on a small preference dataset; measure win-rate shift before/after.
7. **Build an evaluation harness** for a fine-tuned model using `lm-evaluation-harness` or a custom small benchmark (accuracy, exact-match, or LLM-as-judge) — compare base vs fine-tuned vs a bigger reference model.
8. **Build a simple RAG pipeline** over a small document set (your notes, a PDF manual, a FAQ) — chunking, embeddings, vector search, grounded generation.
9. **Hybrid LoRA + RAG assistant** — fine-tune style/format behavior with LoRA while RAG supplies up-to-date factual grounding (e.g. a support-doc assistant).
10. **Distributed-training mini-experiment** — use DeepSpeed ZeRO or Hugging Face Accelerate to fine-tune a mid-size model across multiple (even simulated/free) GPUs, and read EleutherAI's Transformer Math 101 first to predict memory usage before running it.
11. **Quantize and deploy** — take a fine-tuned model, quantize it to GGUF/AWQ/GPTQ, and serve it locally via Ollama or `llama.cpp`; compare latency/quality trade-offs across quant levels.

---

## 13. Datasets & Model Hubs

### Pretraining-scale datasets

| Dataset | Description | Cost |
|---|---|---|
| [FineWeb (Hugging Face)](https://huggingface.co/datasets/HuggingFaceFW/fineweb) | 15T-token filtered/deduplicated English web corpus (96 Common Crawl snapshots); currently a top open pretraining corpus. | Free |
| [RedPajama-V2 (GitHub / Together)](https://github.com/togethercomputer/RedPajama-Data) — [blog](https://www.together.ai/blog/redpajama-data-v2) | 30T-token, multilingual, richly annotated open pretraining dataset from Common Crawl. | Free |
| [The Pile (EleutherAI)](https://pile.eleuther.ai/) | Classic 825GB/~825B-token diverse 22-source corpus; smaller/older but still a useful research baseline. | Free |

### Instruction / fine-tuning datasets & model hubs

| Resource | Description | Cost |
|---|---|---|
| [Hugging Face Hub — Datasets](https://huggingface.co/datasets) | The primary hub for instruction-tuning, preference, and evaluation datasets (Alpaca, Dolly, UltraChat, UltraFeedback, OpenOrca, etc.). | Free |
| [Hugging Face Hub — Models](https://huggingface.co/models) | The primary hub for open-weight base and fine-tuned models across all sizes/architectures, incl. GGUF quantized checkpoints. | Free |
| [Ollama model library](https://ollama.com/library) | Curated library of ready-to-run quantized open models for local inference/fine-tuning experiments. | Free |
| [LM Studio](https://lmstudio.ai/) | GUI app for discovering/running GGUF models locally, pulls directly from Hugging Face. | Free |

---

## 14. Cheat Sheets / Quick References / Glossaries

| Resource | Description | Cost |
|---|---|---|
| [Abonia1/CheatSheet-LLM (GitHub)](https://github.com/Abonia1/CheatSheet-LLM) | Community-maintained LLM cheat sheet covering core terms, training stages, and techniques. | Free |
| [FM Cheat Sheet — Foundation Model Resources](https://fmcheatsheet.org/foundation-model-resources/model-training-educational-resources/) | Curated list of foundation-model training educational resources and reference material. | Free |
| [EleutherAI — Transformer Math 101](https://blog.eleuther.ai/transformer-math/) | Doubles as a quick-reference formula sheet for compute/memory estimation during training. | Free |
| [Hugging Face LLM Course — Glossary/terms embedded per chapter](https://huggingface.co/learn/llm-course/en/chapter1/1) | Inline glossary-style definitions as part of the course content. | Free |
| [roadmap.sh — AI Engineer Roadmap](https://roadmap.sh/ai-engineer) | Visual, checklist-style roadmap connecting LLM/AI-engineering concepts in a suggested learning order. | Free |

---

## 15. Suggested Learning Progression

### Beginner
1. Skim **3Blue1Brown Neural Networks** series for intuition (§1).
2. Do **Karpathy's Zero to Hero**: micrograd → makemore (§2/§8) — this alone teaches backprop, language modeling basics, and sets up everything else.
3. Read **The Illustrated Transformer** and **The Illustrated GPT-2** (§5) alongside skimming **Attention Is All You Need** (§5).
4. Work through the **Hugging Face LLM Course** chapters 1–3 (transformers pipeline, tokenizers, fine-tuning basics) (§2).

### Intermediate
5. Finish **Zero to Hero**: build GPT from scratch + build the GPT tokenizer (§2/§5/§8).
6. Read **Sebastian Raschka's "Build a Large Language Model From Scratch"** and work through the companion repo (§6/§8) — pretraining, classification fine-tuning, instruction fine-tuning.
7. Read the **scaling laws** (Kaplan) and **Chinchilla** papers, plus **EleutherAI's Transformer Math 101** for compute/memory intuition (§5).
8. Do a hands-on **LoRA fine-tune** on a small open model using an Unsloth or PEFT notebook on free Colab/Kaggle GPU (§7/§12).
9. Read **InstructGPT**, **FLAN**, and **DPO** papers to understand the post-training landscape (§5).

### Advanced
10. Read/skim **rlhfbook.com** end to end for the full RLHF/post-training picture (§6).
11. Reproduce **GPT-2 (124M)** using Karpathy's video/repo on a rented or free-tier GPU (§2/§8).
12. Run a **QLoRA fine-tune** of a 7B model, then a **DPO** pass with TRL (§8/§12).
13. Study **DeepSpeed**/**Megatron-LM**/**GPT-NeoX** source and EleutherAI's cookbook for distributed-training internals (§8).
14. Build an **evaluation harness** (lm-evaluation-harness or custom) and a **RAG + LoRA hybrid** project to tie everything into an applied system (§8/§12).
15. Go deep on frontier discussion via **CS25: Transformers United**, **CS324**, and the **Dwarkesh**/**Latent Space** podcasts to stay current (§2/§11).

---

*This document is a resource catalog for future curriculum-building — it intentionally does not contain tutorials or step-by-step lessons itself.*
