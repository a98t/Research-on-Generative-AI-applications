# Vocabulary: GenAI Application Development (Starter Glossary)

This file is a living glossary. Each definition is written in plain language and grounded in the use‑cases from the research report. Add, prune, and refine as you learn more.

## Core Concepts

**RAG (Retrieval‑Augmented Generation).** Retrieve relevant documents and feed them into the prompt so the model answers with grounded, citable context rather than guessing.

**Grounding.** Constraining model output to trusted sources (retrieved documents, tools, APIs) so answers are accurate and auditable.

**Hallucination.** A fluent but incorrect or unfounded output produced by a model; mitigated by grounding, guardrails, and evaluations.

**Context Window.** The maximum token capacity a model can “see” at once (prompt + response); larger windows allow more files and examples but can increase cost/latency.

**Tokens.** The sub‑word units models use internally. Token counts drive cost, context limits, and sometimes quality.

**Embedding.** Dense vector representation of text/images used to measure similarity and power search/ranking in a vector database.

**Vector Database.** Store optimized for fast nearest‑neighbor lookups over embeddings (e.g., FAISS, Pinecone) to enable retrieval for RAG.

**Chunking.** Splitting source documents into retrieval‑friendly pieces (by size or semantic boundaries) to improve hit rate and answer quality.

**Reranking.** A second‑stage scoring step that reorders retrieved chunks by relevance using a stronger model.

**Freshness.** Ensuring retrieved data isn’t stale (e.g., re‑indexing schedules, time‑aware ranking) so answers reflect current truth.

**Prompt Engineering.** Crafting instructions, roles, examples, and constraints that guide models toward desired outputs.

**System Prompt.** The hidden “role + rules” message that sets model behavior, tone, and boundaries for an assistant/agent.

**Temperature.** Sampling control for randomness; higher values increase diversity/creativity, lower values improve determinism/consistency.

**Top‑p (Nucleus Sampling).** Sample from the smallest set of tokens whose cumulative probability ≥ p; balances variety and coherence.

**Guardrails.** Policies, filters, and validators (e.g., safety, compliance, brand style) that accept/transform/block model outputs.

**Alignment.** Techniques that make models helpful, honest, and safe (e.g., RLHF, constitutional prompting, safety training).

**Evaluation (Eval Harness).** Automated checks and metrics (accuracy, groundedness, toxicity, latency, cost) to monitor quality and regressions.

**Red Teaming.** Adversarial testing to probe for failures (bias, jailbreaks, data exfiltration) before and after launch.

**Jailbreak.** A prompt or technique that bypasses safety constraints; defend with filtering, instruction hardening, and detectors.

**Latency.** Time to get the first/complete token response; influenced by model size, context length, retrieval hops, and network.

**Throughput.** Number of requests served per second across concurrent users; a core capacity‑planning metric.

**Cost per Token.** Unit cost used to estimate spend; minimized via shorter prompts, retrieval selectivity, caching, and smaller models where viable.

**Observability.** Telemetry across prompts, inputs/outputs, retrieval, and tool calls to debug incidents, quality, and cost.

**Data Governance.** Policies for privacy, retention, PII redaction, and access controls across prompts, logs, embeddings, and stores.

## Application‑Specific Terms

**Diarization.** Separating speakers in audio so transcripts and action items map to the right person (useful for meeting notes and scribing).

**Temporal Consistency.** Preserving object identity and smooth motion across video frames; a common challenge in text‑to‑video.

**Brand Voice.** Enforcing a consistent tone/style across generated marketing copy (usually via system prompts + memory).

**Row‑Level Security (RLS).** Limiting which data rows a user/model can access; critical for NL‑to‑BI and RAG on private data.

**Semantic Layer.** Business definitions/metrics that map natural language to the correct tables/joins/measures in analytics.

**Provenance.** Traceability of where information/code comes from (sources, licenses), important for audits and code suggestions.

**Watermarking.** Marking synthetic audio/images/video so downstream systems can detect AI‑generated media.

**PII Redaction.** Removing personally identifiable information from prompts, documents, and logs to reduce leakage risk.

**Chunk‑to‑Answer Trace.** Showing which retrieved chunks supported each sentence in the answer (explainability).

**Quality Gates.** Pre‑production or runtime checks that block outputs unless they meet thresholds (e.g., groundedness ≥ X).

## Developer Workflow & Coding Assistants

**IDE Integration.** Running the assistant inside editors (VS Code, JetBrains, Android Studio) for inline suggestions and refactors.

**Code Provenance.** Tracing licenses/origin of generated code snippets; review for compliance before merging.

**Prompt Contextualization.** Supplying the model with project‑wide files, schema, or issue history to improve relevance of code suggestions.

**Scaffold Generation.** Generating boilerplate (tests, handlers, API routes, config) to speed up feature starts.

**Review Assist.** Using models to summarize diffs, highlight risks, suggest tests, and spot security/performance issues.

**Test Synthesis.** Generating unit/integration tests from specs or code to improve coverage and catch regressions.

## Data & Infra

**Firestore.** A serverless NoSQL document database (Firebase) with real‑time sync; often used with mobile/web apps.

**Indexing Strategy.** Designing composite indexes and filters to keep Firestore (or any DB) queries fast and cost‑efficient.

**RPS/QPS (Requests per Second).** Load measurement for sizing autoscaling, rate limits, and cost models.

**Cold Start.** Latency spike when serverless functions scale from zero; mitigated by warmers or minimum instances.

## Named Tools (for quick reference)

**Gemini Code Assist.** Google’s AI‑powered coding assistant that generates, explains, and refactors code inside IDEs.

**Firebase Studio.** Web‑based Firebase environment with Gemini integration to generate code, update files, and help with Firestore/Cloud Functions.

**Cursor.** An AI‑powered coding editor that explains, edits, and generates code using natural‑language prompts while keeping project context.

**GitHub Copilot.** In‑IDE assistant for code/tests/explanations trained on public code + enterprise features for private repos.

**Amazon Q Developer.** AWS’s developer assistant for code, tests, and cloud changes with deep integration into AWS tooling.

---