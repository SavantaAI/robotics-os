---

description: Welcome to your team’s developer platform
layout:
width: wide
title:
visible: false
description:
visible: false
tableOfContents:
visible: false
outline:
visible: false
pagination:
visible: false
metadata:
visible: true
-------------

# Developer Platform

<h2 align="center">Robotics Operating System</h2>

<p align="center">Create &#x26; test robots in minutes — from camera to workflow to real-world execution.</p>

<p align="center"><a href="https://your-app.link/signup" class="button primary">Sign up</a> <a href="https://your-app.link/login" class="button secondary">Log in</a></p>

---

## 1) What is this product?

**A modular “robot OS” for doers.**
It fuses 3 pillars:

1. **Perception** — a multimodal model that understands objects *and* their useful properties (distance, motion/speed, temperature class via thermal, weight class via size+density priors).
2. **Planning & Workflow** — a visual, n8n-style **Behavior Tree Studio** for composing tasks with guardrails and fallbacks.
3. **Execution & Simulation** — one-click **Sim→Real**: dry-run in high-fidelity sim, then deploy to your ROS 2 stack on real hardware.

**Who it’s for:** founders, ops teams, integrators, and researchers who want plug-and-play robotics without rebuilding middleware from scratch.

---

## 2) Key features & differentiators

<table data-view="cards"><thead><tr><th></th><th></th><th></th><th data-hidden data-card-target data-type="content-ref"></th><th data-hidden data-card-cover data-type="files"></th></tr></thead><tbody>

<tr>
<td><h4>🧠</h4></td>
<td><strong>Task-relevant perception</strong></td>
<td>Out-of-the-box heads for distance, motion, temperature class (hot/neutral/cold via thermal), and weight class (size + material priors). Designed for decisions, not just labels.</td>
<td><a href="https://docs.your-site/perception">Perception docs</a></td>
<td><a href=".gitbook/assets/perception.png">perception.png</a></td>
</tr>

<tr>
<td><h4>🧩</h4></td>
<td><strong>Behavior Tree Studio</strong></td>
<td>No-code node editor that composes actions, policies, and perception into safe, debuggable workflows. Export/import as BT XML; runs atop ROS 2, Nav2, MoveIt.</td>
<td><a href="https://docs.your-site/workflows">Workflow guide</a></td>
<td><a href=".gitbook/assets/bt-studio.png">bt-studio.png</a></td>
</tr>

<tr>
<td><h4>🖥️</h4></td>
<td><strong>Sim→Real by design</strong></td>
<td>Record/replay scenes, generate synthetic data, and validate the exact workflow in sim before enabling motors. Domain randomization and safety linting included.</td>
<td><a href="https://docs.your-site/simulation">Simulation</a></td>
<td><a href=".gitbook/assets/sim.png">sim.png</a></td>
</tr>

<tr>
<td><h4>🛡️</h4></td>
<td><strong>Safety guardrails</strong></td>
<td>Speed/joint limits, proximity rules, capability-scoped nodes, and human-in-the-loop confirmations. Red-button hard stops + software watchdogs.</td>
<td><a href="https://docs.your-site/safety">Safety</a></td>
<td><a href=".gitbook/assets/safety.png">safety.png</a></td>
</tr>

<tr>
<td><h4>🛒</h4></td>
<td><strong>Marketplace (alpha)</strong></td>
<td>Certified task packs (pick-place, sorting by temp/weight, hot-tray handling). Revenue share for developers; capability manifests keep deployments safe.</td>
<td><a href="https://docs.your-site/marketplace">Marketplace</a></td>
<td><a href=".gitbook/assets/marketplace.png">marketplace.png</a></td>
</tr>

<tr>
<td><h4>🔌</h4></td>
<td><strong>Hardware-friendly</strong></td>
<td>ROS 2 drivers and templates for common arms and mobile bases; reference sensor kit (RGB-D + thermal) and optional tactile/scale add-ons for calibration.</td>
<td><a href="https://docs.your-site/hardware">Hardware</a></td>
<td><a href=".gitbook/assets/hardware.png">hardware.png</a></td>
</tr>

</tbody></table>

---

## 3) Ecosystem & platform vision

**A full loop where each part strengthens the others:**

* **Perception engine** improves through synthetic + real data, then serves richer signals (e.g., “object is hot & light”).
* **BT Studio** lets anyone wire those signals into tasks with retries, fallbacks, and guardrails.
* **Simulation** validates tasks, generates new edge cases, and feeds the perception engine fresh labels.
* **Marketplace** distributes proven behaviors so integrators ship faster and earn from their playbooks.
* **Hardware integrations** keep friction low: standard interfaces, calibration wizards, and example projects.

**Open where it matters:** ROS 2 compatible, BT XML import/export, SDK for custom nodes, and data connectors for your MLOps stack.

---

## 4) Roadmap / current status / scope

**Now (Pilot Program):**

* Perception v0 (distance, motion, temp-class via thermal, weight-class via size+density priors).
* BT Studio v0 (core nodes, guards, logging, sim dry-run).
* Reference hardware kit (RGB-D + thermal; UR/RO1 class arms).
* 3 pilot templates: *Hot-Tray Handover*, *Weight-Sorted Kitting*, *Follow-and-Handover (moving target)*.

**Next 3–6 months:**

* Sim pipeline with synthetic data generator and record/replay.
* Safety linter: speed/joint envelopes, proximity rules, two-person confirm nodes.
* Marketplace (closed alpha) for certified task packs.

**6–12 months:**

* Perception v1 (few-shot adapters on customer sites, better material priors).
* Fleet ops: job queueing, remote logs, versioned workflow rollouts.
* Expanded hardware modules + partner drivers.

**Scope & principles:**

* Build on ROS 2, Nav2, MoveIt.
* Multimodal by default (RGB-D + thermal), tactile optional.
* “Sim before spin”: no workflow runs on hardware without a matching sim pass.

---

## 5) TL;DR + ecosystem diagram

**You bring a robot and a task. We bring perception, a friendly workflow editor, and a safety-first path from sim to real. Share or sell your workflows in the marketplace and compound the ecosystem.**

```mermaid
flowchart LR
    subgraph Data & Sim
      A[Scene Generator\n(Synthetic, Record/Replay)] --> B[Labeler\nRGB-D-Thermal, Motion, Size]
      B --> C[Perception Training\n(Weight/Temp/Motion/Distance Heads)]
    end

    subgraph Runtime
      C --> D[Perception Runtime\nROS 2 Nodes]
      D --> E[Blackboard / Scene Graph\n(Objects, Properties, Zones)]
      E --> F[Behavior Tree Studio\n(No-code + XML)]
      F --> G[Planners & Control\nNav2, MoveIt, Custom Nodes]
      G --> H[Robot Hardware\nArms, Bases, I/O]
    end

    subgraph Safety & Ops
      I[Safety Linter\nLimits, Proximity, Confirms] --> F
      J[Versioning & Rollouts] --> F
      K[Telemetry & Logs] --> F
    end

    subgraph Marketplace
      L[Certified Task Packs] --> F
      F --> M[Publish/Share]
    end

    Data & Sim --- Runtime
    Runtime --- Safety & Ops
    Marketplace --- Runtime
```

---

{% columns %}
{% column %}

### Get started in 5 minutes

Pick a hardware profile, connect your sensors, and open the BT Studio. Use a template, hit *Simulate*, then deploy to your ROS 2 graph.

<a href="https://your-app.link/start" class="button primary" data-icon="rocket-launch">Get started</a> <a href="https://your-app.link/api" class="button secondary" data-icon="terminal">API reference</a>
{% endcolumn %}

{% column %}
{% code title="Example: spawn a workflow (TypeScript SDK)" overflow="wrap" %}

```ts
import { Client } from "@yourorg/robot-os";

const sdk = new Client({ apiKey: process.env.API_KEY });

const wf = await sdk.workflows.create({
  name: "Hot-Tray Handover",
  hardwareProfile: "ur10e_rgbd_thermal",
  template: "hot_tray_handover_v1",
  safety: { requireHumanConfirm: true }
});

await sdk.workflows.simulate(wf.id, { scene: "kitchen_line_a" });
await sdk.workflows.deploy(wf.id, { robotId: "ROBOT-001" });
```

{% endcode %}
{% endcolumn %}
{% endcolumns %}

{% columns %}
{% column %}

<figure>
  <img src=".gitbook/assets/hero.png" alt="">
  <figcaption>From Sim → Real in one click.</figcaption>
</figure>
{% endcolumn %}

{% column %}

### Learn more

Guides, hardware profiles, and step-by-step tutorials to go from idea to on-site pilot.

<a href="https://your-app.link/guides" class="button primary" data-icon="book-open">Guides</a> <a href="https://your-app.link/docs" class="button secondary" data-icon="book">Documentation</a>
{% endcolumn %}
{% endcolumns %}

---

### Community

<table data-card-size="large" data-view="cards"><thead><tr><th></th><th></th><th></th><th></th></tr></thead><tbody>
<tr><td><h4>💬</h4></td><td><strong>Discord</strong></td><td>Get help, share workflows, and showcase builds.</td><td><a href="https://your-community.link" class="button secondary">Join Discord</a></td></tr>
<tr><td><h4>🌟</h4></td><td><strong>GitHub</strong></td><td>SDKs, examples, and issue tracking.</td><td><a href="https://github.com/yourorg/robot-os" class="button secondary">View repo</a></td></tr>
</tbody></table>

---

**Q1**

What single “day-one” template should appear in the BT Studio for your pilot (e.g., *Hot-Tray Handover*, *Weight-Sorted Kitting*, or *Follow-and-Handover*)?

**Q2**

Which hardware profile do you want first-class: UR10e + RGB-D + thermal, or another arm/base combo you already own?

**Q3**

Do you prefer closed-alpha Marketplace with curated packs, or open submissions with stricter certification gates from the start?
