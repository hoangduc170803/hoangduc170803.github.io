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

<div class="swes-demo">
  <video autoplay loop muted playsinline
         poster="{{ '/assets/img/swes_demo_poster.jpg' | relative_url }}">
    <source src="{{ '/assets/video/swes_demo.mp4' | relative_url }}" type="video/mp4">
  </video>
  <p class="caption">
    The full run, roughly 48x real time. Orders drain from the upper block while completed
    stock accumulates in the lower one, and vehicles run the corridor between the racking and
    the station at the far left. Each vehicle draws the route the planner assigned it.
  </p>
</div>

<style>
  .swes-demo { margin: 1.5rem 0 2rem; text-align: center; }
  .swes-demo video {
    max-width: 100%; width: 100%; height: auto;
    border: 1px solid var(--global-divider-color); border-radius: 4px;
  }
  .swes-demo .caption {
    font-size: 0.85rem; color: var(--global-text-color-light);
    margin: 0.6rem auto 0; max-width: 34rem; line-height: 1.5;
  }
</style>

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
