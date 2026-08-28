# AI Engineering Mastery Roadmap

---

## Phase 0 — Foundations (don't skip)

- **Math**: linear algebra (matrix ops, eigenvectors), probability/statistics, calculus (gradients), information theory (entropy, KL divergence)
- **Programming**: Python (async/await, typing, packaging), Git, Docker/containers, Linux/CLI basics
- **Classical ML**: bias-variance, regularization, loss functions, optimization (SGD, Adam)
- **Deep Learning core**: backprop, CNNs/RNNs (context, not depth), the **Transformer architecture** (attention, positional encoding, layer norm, KV cache) — this is the single most important thing to deeply understand

## Phase 1 — LLM Pre-training (the "pre" in pre/mid/post)

- Tokenization (BPE, SentencePiece), vocabulary design
- Pretraining objectives (causal LM, masked LM)
- Scaling laws (Chinchilla, compute-optimal training)
- Data pipelines for pretraining: web-scale crawling, dedup, filtering, quality scoring
- Distributed training: data/tensor/pipeline parallelism, ZeRO/FSDP, mixed precision
- Infra: multi-GPU/multi-node training, checkpointing, cluster orchestration

## Phase 2 — Mid-training & Post-training

- **Mid-training**: continued pretraining, domain adaptation, context-length extension (RoPE scaling, long-context tricks)
- **Post-training**:
    - Supervised Fine-Tuning (SFT)
    - Preference optimization: RLHF (PPO), DPO, KTO, GRPO
    - Reward modeling
    - Synthetic data generation & distillation
    - Instruction tuning, chat templates

## Phase 3 — Fine-tuning (applied)

- Full fine-tuning vs parameter-efficient (LoRA, QLoRA, adapters, prefix-tuning)
- Dataset curation for fine-tuning (quality > quantity), data mixing
- Evaluation before/after fine-tuning (avoiding regression/catastrophic forgetting)
- When to fine-tune vs prompt vs RAG (decision framework this trips up most engineers)

## Phase 4 — Inference & Prompting

- **Prompt engineering** (few-shot, CoT, structured outputs, system prompts)
- **Context engineering** (broader discipline beyond prompting — what goes into the context window and why)
- Inference optimization: quantization (GPTQ/AWQ/GGUF), vLLM/TGI serving, speculative decoding, batching, KV-cache management
- Sampling strategies (temperature, top-p, top-k, structured decoding/grammars)

## Phase 5 — RAG (Retrieval-Augmented Generation)

- **Embeddings** (dense, sparse, hybrid search)
- **Vector databases** (Pinecone, Weaviate, Qdrant, pgvector, FAISS)
- Chunking strategies, re-ranking, query rewriting/expansion
- **Advanced RAG:** GraphRAG, agentic RAG, multi-hop retrieval
- **RAG evaluation** (retrieval precision/recall, faithfulness, RAGAS)

## Phase 6 — Agentic AI

- Tool use/function calling, structured tool schemas
- **Loop engineering** — designing the agent's think→act→observe loop (ReAct, plan-and-execute, reflection loops), managing loop termination, cost/step budgets
- **Harness engineering** — building the scaffolding an agent runs inside: sandboxed execution environments, test harnesses, eval harnesses (SWE-bench-style), tool simulators
- Memory systems (short-term/episodic, long-term/vector memory, working memory management)
- Multi-agent orchestration (handoffs, supervisor patterns, frameworks: LangGraph, CrewAI, AutoGen, OpenAI Agents SDK)
- Planning & task decomposition

## Phase 7 — LLM Guardrails & Safety

- Input/output guardrails (PII detection, jailbreak/prompt-injection defense, content filtering)
- Red-teaming and adversarial testing
- Structured output validation, hallucination detection
- Guardrail frameworks (Guardrails AI, NeMo Guardrails, Llama Guard)

## Phase 8 — LLM Gateways

- Unified API routing across providers (LiteLLM, Portkey, OpenRouter)
- Rate limiting, load balancing, fallback/retry logic across models
- Caching (semantic caching), cost tracking, API key management
- Multi-tenant access control

## Phase 9 — Observability & Evaluation

- Tracing (spans for LLM calls, tool calls, retrieval steps) — LangSmith, Langfuse, Arize Phoenix, Helicone
- Logging, latency/cost/token monitoring
- Evaluation frameworks: offline evals, online A/B testing, LLM-as-judge, human eval loops
- Drift detection, regression testing for prompts/models

## Phase 10 — LLMOps & MLOps

- CI/CD for prompts and models (prompt versioning, model registries)
- Experiment tracking (MLflow, Weights & Biases)
- Feature stores, data versioning (DVC)
- Deployment strategies: canary, shadow, blue-green for model rollouts
- Cost optimization at scale (routing to cheaper models, caching, batching)

## Phase 11 — Cloud Platforms (AWS / Azure / GCP)

- **AWS**: SageMaker, Bedrock, EC2/GPU instances, S3, Lambda for serverless inference
- **Azure**: Azure ML, Azure OpenAI Service, AKS
- **GCP**: Vertex AI, TPUs, GKE
- Infra-as-code (Terraform), Kubernetes for model serving, autoscaling GPU workloads

## Phase 12 — Security & Production Hardening

- Prompt injection & data exfiltration defense (ties back to guardrails, deeper here)
- Secrets management, network isolation for agentic tool access
- Compliance (SOC2, GDPR considerations for AI systems)
- Model/data supply-chain security

## Phase 13 — System Design for AI Products

- Designing end-to-end AI systems (chat assistant, RAG pipeline, agent platform) under real constraints
- Latency/cost/quality trade-off design
- Case studies: how to architect a production copilot, a support-agent system, a coding agent

---

## Topics you didn't list but need for mastery

- **Transformer internals & attention mechanics** (Phase 0) — foundation everything else sits on
- **Embeddings deep-dive** — separate from RAG; matters for search, clustering, dedup
- **Model evaluation/benchmarking theory** (perplexity, benchmark suites like MMLU, HELM) — distinct from LLM observability
- **Synthetic data generation & distillation** — critical for both training and fine-tuning
- **Quantization & model compression** — often skipped, essential for cost/latency
- **Context engineering** — increasingly treated as its own discipline separate from prompting
- **Human-in-the-loop design** — feedback collection, active learning loops
- **Cost/FinOps for AI systems** — token economics, GPU cost modeling
- **Multi-modal models** (vision-language, audio) — if your scope extends beyond text
- **Interpretability/mechanistic interpretability** — increasingly relevant for research-track engineers

---

## Suggested learning order (condensed)

1. Foundations → 
2. Pretraining → 
3. Mid/Post-training → 
4. Fine-tuning → 
5. Inference & Prompting → 
6. RAG → 
7. Agentic AI (loop + harness eng) → 
8. Guardrails → 
9. Gateways → 
10. Observability & Eval → 
11. LLMOps → 
12. Cloud → 
13. Security → 
14. System Design →
