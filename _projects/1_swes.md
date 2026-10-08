---
layout: page
title: SWES
description: Multi-agent path finding for a live AGV fleet, inside the openTCS kernel
importance: 1
category: work
permalink: /projects/swes/
tag: "Aubot"
period: "2026"
headline: "SWES - Smart Warehouse Execution System (Multi-AGV Orchestration)"
stack: "openTCS - PIBT / LaCAM / LaCAM* - Action Dependency Graph - Hungarian algorithm"
---

**SWES — Smart Warehouse Execution System (Multi-AGV Orchestration)**
Research and Development, Multi-Agent Path Finding · Aubot (CF Group) · June – August 2026
Graduation capstone project, graded 9.0/10 (A+).

### The problem

openTCS, the industrial control kernel the fleet runs on, ships with a Dijkstra router that plans each
vehicle independently. Single-agent shortest paths say nothing about what the other vehicles are doing, so
in regular operation the AGVs deadlocked against one another in the aisles.

### What I built

A joint multi-agent planner inside the openTCS Java kernel, developed through a progression of published
methods: **PIBT**, then **LaCAM**, then **LaCAM\***. I extended it to continuous order arrival using
**LLLG local guidance** (SoCS-26) and an **Action Dependency Graph** to prevent corridor deadlock.

### Getting it onto real vehicles

The published algorithms assume an undirected graph and dimensionless agents. A warehouse is neither. I
ported them onto a **directed industrial roadmap** that accounts for vehicle footprints and headings, and
replaced the greedy task assignment with **global min-cost matching** using the Hungarian algorithm over
road-graph distances.

### Outcome

Deployed on Aubot's live AGV fleet.
