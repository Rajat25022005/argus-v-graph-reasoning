# Argus-V  
**Spatio-Temporal Graph Reasoning Engine for Video Understanding**

Argus-V is a research-oriented multi-modal AI system designed to move video analysis beyond object detection toward **causal, identity-aware, and temporally grounded reasoning**. Instead of treating video as isolated frames, Argus-V converts video into a **structured knowledge graph**, enabling AI systems to answer questions about *what happened, in what order, who was involved, and why*.

---

## Motivation

Most modern video AI systems excel at detecting objects or recognizing actions but fail to:
- Connect events across time  
- Attribute actions to specific identities  
- Explain causal chains behind outcomes  

In real-world, high-stakes domains such as **medical safety, forensics, and trustworthy AI**, these limitations prevent meaningful accountability and analysis. Argus-V addresses this gap by unifying perception, memory, and reasoning.

---

## Core Idea

**Video is treated as empirical evidence, not just visual data.**

Argus-V transforms raw video into:
- Entities (people, objects, locations)
- Events (actions with timestamps)
- Relationships (temporal order, interaction, causality)

These are stored in a **knowledge graph**, allowing deterministic, auditable reasoning instead of probabilistic hallucination.

---

## System Architecture

Argus-V follows a three-layer architecture:

### 1. Perception Layer (Eyes)
- **V-JEPA** – spatio-temporal and physical feature extraction  
- **DeepFace** – biometric identity grounding  
- **Florence-2 / LLaVA** – action and scene captioning  

### 2. Knowledge Layer (Memory)
- **Neo4j Graph Database**
- Nodes: Person, Object, Event, Location, TimeFrame  
- Edges: INTERACTED_WITH, BEFORE, CAUSED, TRIGGERED  

Example:

> (Rajat) -[:PICKED_UP]-> (Laptop) -[:AT_TIME]-> (00:14)


### 3. Reasoning Layer (Brain)
- **GraphRAG (LangGraph)** for query-to-graph translation  
- **LLM (Llama-3)** for natural-language forensic explanations  

---

## Example Query

**User Question:**  
> Why did the fire alarm go off?

**Graph Reasoning Path:** 
> Alarm ← TRIGGERED ← Smoke ← EMITTED_BY ← Machine ← OVERHEATED_AT ← 10:00


**System Answer:**  
> The fire alarm was triggered by smoke emitted from Machine B after it overheated at 10:00 AM.

---

## Technical Stack

- Video Understanding: Meta V-JEPA  
- Face Recognition: DeepFace  
- Vision-Language Model: Florence-2 / LLaVA  
- Graph Database: Neo4j  
- Orchestration: LangGraph  
- LLM Reasoning: Llama-3  
- Runtime: Python, PyTorch, CUDA  

---

## Hardware Requirements

- **GPU:** Single GPU with **≥24 GB VRAM** (RTX 4090, A10, L4, A100)
- **CPU:** Standard x86_64
- **OS:** Ubuntu 20.04+
- The system is **inference-focused** and does not require training models from scratch.

---

## Key Contributions

- **Causal Graph Reasoning** over video instead of similarity-based retrieval  
- **Identity Grounding** for accountability and auditability  
- **Zero-Shot Forensics** — no retraining required per video  
- **Separation of perception and reasoning**, improving interpretability  

---

## Current Status

- Architecture finalized  
- Inference pipeline implemented  
- Graph-based reasoning operational  
- Ongoing experiments and optimization  

---

## Future Work

- Real-time RTSP / CCTV stream ingestion  
- Audio-visual fusion using Whisper  
- Counterfactual reasoning over event graphs  
- Deployment in safety-critical environments  

---

## License

This project is licensed under the **MIT License**.

---

## Contact

**Rajat Malik**  
Department of Computer Science  
Chandigarh University  

This repository represents ongoing research. Feedback, discussion, and collaboration are welcome.
