---
layout: page
title: Hybrid RAG
description: Answering policy questions from internal documents, with traceable citations
importance: 2
category: work
permalink: /projects/hybrid-rag/
tag: "Viettel DT"
period: "2025"
headline: "Hybrid RAG over internal policy documents"
stack: "Milvus - BGE-M3 - BM25 - Gemma 3 - FastAPI - Docker"
---

**Hybrid RAG System**
Viettel Digital Talent Program · April – June 2025
Python · FastAPI · Streamlit · Milvus · MinIO · Docker · BGE-M3 · Gemma 3

### The problem

The company issues a large body of internal policies. Staff could rarely tell which one governed their
particular case, and keyword search over the documents was not good enough to settle the question.

### What I built

A retrieval system that answers which company-issued policy applies and returns the governing document
alongside the answer. Documents are indexed with **BGE-M3 embeddings** (1024-dimensional) in **Milvus**,
and dense vector search is combined with **BM25** sparse retrieval, which improved both recall and the
quality of the ranking over either method alone.

**Gemma 3** models serve as the generative backbone, benchmarked across model sizes. Every answer carries
a citation back to the source document, which matters here: with policy text, a reader has to be able to
check where an answer came from.

All services — FastAPI, Streamlit, Milvus, MinIO and Etcd — are containerised with Docker Compose and
health monitoring.

### Why it mattered to me

This project was where the two halves of my work met. The model was only as good as the pipeline feeding
it, and that is the problem I want to keep working on.
