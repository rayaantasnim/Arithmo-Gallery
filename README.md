<div align="center">
  <a href="https://github.com/Arithmo-Edge">
    <img src="Assets/Images/The 14-Portal Federated Constellation.webp" alt="Arithmo Edge Logo" width="1200" style="border-radius: 24px; box-shadow: 0 8px 24px rgba(0, 0, 0, 0.25);" />
  </a>

  <h1>Arithmo Edge</h1>
  <p><strong>Powered by Olympiad Edge</strong></p>
  <p><em>The World's First Real-Time ELO-Rated Competitive Mathematics &amp; Olympiad Mega-Ecosystem.</em></p>

  <p>
    <img src="https://img.shields.io/badge/Status-Active%20Development-0ea5e9?style=for-the-badge&logo=github" alt="Status: Active Development" />
    <img src="https://img.shields.io/badge/Architecture-13%20Federated%20Portals-8b5cf6?style=for-the-badge&logo=arquillian" alt="Architecture: 13 Federated Portals" />
    <img src="https://img.shields.io/badge/Verification-SymPy%20%2B%20AI-f59e0b?style=for-the-badge&logo=python" alt="Verification: SymPy + AI" />
    <img src="https://img.shields.io/badge/License-Open%20Ecosystem-10b981?style=for-the-badge&logo=opensourceinitiative" alt="License: Open Ecosystem" />
  </p>

  <br />

  <img src="https://images.pexels.com/photos/7130560/pexels-photo-7130560.jpeg?auto=compress&cs=tinysrgb&w=1600" alt="Arithmo Edge Abstract Mathematical Topology Banner" width="100%" style="border-radius: 12px; max-height: 320px; object-fit: cover;" />
</div>

<br />

## Executive Overview

Competitive programming has thrived for decades on real-time ELO rating systems, live global rounds, and post-match peer hacking through platforms like Codeforces. Meanwhile, competitive mathematics remains trapped between static, 1990s-era asynchronous forums (such as AoPS) and gatekept, $300-$500+ preparatory courses.

Arithmo Edge eliminates that asymmetry. Engineered as a federated, zero-to-low-cost global infrastructure, Arithmo Edge brings sub-second latency, real-time ELO matchmaking, 1v1 Bullet Blitz duels, live Codeforces-style rated contests, peer-hacking phases, and deterministic symbolic verification to pure Olympiad mathematics—making elite mathematical training and verifiable competitive credentials accessible to every student on Earth.

---

## Federated System Architecture

Rather than scaling a brittle monolith, Arithmo Edge operates as 13 independent yet unified web portals orchestrated by a lightweight, zero-dependency Vanilla JS kernel (`Arithmo-Core-SDK / engine.js`). This federated spine enforces global Google OAuth SSO, `@handle` identity routing, strict no-handle auto-redirects, real-time telemetry, and privacy-preserving data ingestion.

<div class="mermaid">
flowchart TB
    subgraph SDK["Centralized Federated Spine: Arithmo-Core-SDK (engine.js)"]
        AUTH["Google OAuth SSO & @handle Routing"]
        TELEM["Global Telemetry, Notifications & TokenMeter"]
    end

    CORE["0. Core Portal\n(Arithmo-Edge.github.io)"]

    subgraph ARENAS["5 Specialized ELO Olympiad Arenas"]
        NT["1. Number Theory\n(Cyan)"]
        ALG["2. Algebra\n(Violet)"]
        GEO["3. Geometry\n(Amber)"]
        COMB["4. Combinatorics\n(Emerald)"]
        MIX["5. Mixed Olympiad\n(Rose)"]
    end

    subgraph LIVE["Real-Time Competition & Verification"]
        CONT["6. Contest Portal\n(1v1 Blitz & 6h Hacking)"]
        FORGE["10. Arithmo Forge\n(Python/SymPy Verification)"]
        MOD7["Module 7 Proctoring\n(4.5s Gaze Guard & 3-Axis Audio)"]
    end

    subgraph ECOSYSTEM["AI, Institutions & Public Standings"]
        STAND["7. Standings Portal\n(14 Live Leaderboards)"]
        AI["8. Arithmo Personal AI\n(Gemini Pro/Flash + Qwen-Math)"]
        ACAD["9. Academy Arena\n(B2B Dual-Handle & KYB)"]
        SOC["11. Arithmo Socials & 12. HQ Core"]
    end

    LAKE["Zero-PII Reasoning Data Lake\n24h Automated JSONL Pipeline"]

    CORE <--> SDK
    SDK <--> ARENAS
    SDK <--> LIVE
    SDK <--> ECOSYSTEM

    CONT <--> MOD7
    CONT <--> FORGE
    FORGE --> LAKE
    CONT --> LAKE
    ARENAS --> LAKE
</div>

---

## Technology Stack & Core Engines

Arithmo Edge is engineered for extreme horizontal scalability, deterministic mathematical rigor, and minimal operational overhead.

| Subsystem | Core Technologies | Architectural Role |
| :--- | :--- | :--- |
| **Frontend UI** | `React`, `Tailwind CSS`, `KaTeX` | High-contrast competitive interfaces with sub-millisecond LaTeX typesetting and 3-column contest workspaces. |
| **Federated SDK** | `Vanilla JS (engine.js)` | Cross-portal state synchronization, `@handle` enforcement, SSO session persistence, and global event bus. |
| **Biometric Anti-Cheat** | `MediaPipe`, `TensorFlow.js` | Browser-native ML execution for Module 7 (4.5s Gaze Guard, 3-Axis Audio Trap, keystroke entropy) with zero raw video upload. |
| **Symbolic Verification** | `Python`, `SymPy` | Deterministic algebraic/number-theoretic proof validation and procedural problem generation in Arithmo Forge. |
| **AI Routing & Socratic Mentor** | `Gemini Pro/Flash`, `Qwen-Math` | Step-by-step Socratic guidance governed by dynamic `TokenMeter` rate-limiting without spoiling solutions. |
| **Edge Proxy & Security** | `Cloudflare Workers`, `AES-256` | Edge API routing, DDoS mitigation, rate-limiting, and encrypted forensic audit storage (Signal Vault). |
| **Database & CI/CD** | `Firebase`, `GitHub Pages & Actions` | Real-time Firestore ELO ledgers, static edge hosting, and 24-hour Zero-PII JSONL data lake pipelines. |

---

## Deep-Dive Architecture & Ecosystem Blueprint

<details>
<summary><strong>1. The 13 Federated Portals (Complete Ecosystem Map)</strong></summary>
<br />

Every portal in the Arithmo Edge network is deployed as a modular micro-frontend bound together by `Arithmo-Core-SDK`:

* **0. Core Portal (`Arithmo-Edge.github.io`):** The central command hub, `@handle` identity onboarding, unified profile analytics, and ecosystem router.
* **1. Number Theory Arena (`/number-theory`):** Cyan-themed specialized training grounds and domain-specific ELO matchmaking.
* **2. Algebra Arena (`/algebra`):** Violet-themed arena dedicated to inequalities, polynomials, functional equations, and abstract structures.
* **3. Geometry Arena (`/geometry`):** Amber-themed arena built for synthetic, projective, and computational Olympiad geometry.
* **4. Combinatorics Arena (`/combinatorics`):** Emerald-themed arena covering graph theory, game theory, extremal principles, and enumerative combinatorics.
* **5. Mixed Olympiad Arena (`/mixed-olympiad`):** Rose-themed full-spectrum IMO, Putnam, and national Olympiad simulation environment.
* **6. Contest Portal (`/contests`):** Real-time rated rounds featuring T-30s pre-match integrity contracts, 3-column expert UI, live clarification queues, 1v1 Bullet Blitz duels, and a 6-hour post-contest Hacking Phase.
* **7. Standings Portal (`/standings`):** Public, frictionless (no-login-required) access to 14 real-time global and domain-specific ELO leaderboards.
* **8. Arithmo Personal AI (`/arithmo-ai`):** Socratic mathematics tutor powered by Gemini Pro/Flash and Qwen-Math with dynamic `TokenMeter` usage governance.
* **9. Academy Arena (`/academy`):** B2B institutional operating system for schools, coaching centers, and math guilds featuring Dual-Handle routing, KYB verification, and automated homework pipelines.
* **10. Arithmo Forge (`/arithmo-forge`):** Deterministic mathematical verification sandbox (Python/SymPy) and collaborative problem-authoring studio.
* **11. Arithmo Socials (`/socials`):** Technical mathematical blogs, peer Q&A, and a transparent Forensic Appeal Portal for anti-cheat audit reviews.
* **12. Headquarters Core (`/hq-core`):** Internal operations war-room, moderator escalation ladder, and ecosystem governance console.

</details>

<details>
<summary><strong>2. Module 7 &amp; Arithmo Forge (Zero-Cheat &amp; Deterministic Verification)</strong></summary>
<br />

Remote mathematical competitions fail without airtight integrity and contamination-free problems. Arithmo Edge solves both at the architectural layer:

* **Module 7 (Browser-Native Biometric Proctoring):**
  * **Zero-Server Video Streaming:** Executes `MediaPipe` and `TensorFlow.js` inference entirely client-side inside the participant's browser, preserving student privacy while eliminating cloud GPU bottlenecks.
  * **4.5-Second Gaze Guard:** Detects sustained off-screen visual deviation or secondary device reference in real time.
  * **3-Axis Audio Trap & Telemetry:** Monitors acoustic anomalies, tab-switch focus loss, and keystroke/backspace entropy patterns to flag external AI assistance.
  * **AES-256 Signal Vault:** Cryptographically signs and seals forensic telemetry logs for deterministic review during post-contest audits and appeals.
* **Arithmo Forge & The 5-Pillar Legal Problem Engine:**
  * **Golden Repository:** Pairs human-authored Olympiad seed templates with procedural `Python/SymPy` generators to synthesize millions of original, contamination-free problem variants.
  * **Deterministic Verification:** Evaluates symbolic equivalence, boundary conditions, and multi-step derivations deterministically—eliminating grading ambiguity.
* **Zero-PII Reasoning Data Lake:**
  * Every 24 hours, automated GitHub Actions workflows scrub all Personally Identifiable Information (PII) and export verified human proof trajectories, solve latencies, and error-recovery steps into clean `JSONL` datasets.

</details>

<details>
<summary><strong>3. The 20-Year Holding Vision (8 Autonomous Deep-Tech Spin-Offs)</strong></summary>
<br />

Designed with strict API boundaries from Day 1, Arithmo Edge is structured as an Alphabet-style holding architecture engineered to incubate and spin off 8 autonomous deep-tech enterprises over a 5-to-20-year horizon:

1. **AI Reasoning Data Lab:** Licensing verified, contamination-free human mathematical reasoning `JSONL` trajectories to frontier AI research labs.
2. **Zero-Cheat Proctoring SaaS (Module 7):** B2B privacy-first, browser-native biometric exam integrity infrastructure for universities and enterprise certifications.
3. **Quant & Deep-Tech Recruitment Network:** Direct talent pipeline connecting top ELO-rated problem solvers with quantitative trading firms and frontier research labs.
4. **Institutional EdTech SaaS (Academy Arena):** Global digital infrastructure for math circles, secondary schools, and national Olympiad training camps.
5. **Deterministic Math Verification API (Arithmo Forge):** Neuro-symbolic verification middleware preventing mathematical hallucinations in enterprise LLM workflows.
6. **Global Competitive League & Media:** Sponsored international mathematical tournaments, university leagues, and live 1v1 e-sports-style broadcasts.
7. **Personalized Socratic AI Tutor:** Consumer-grade adaptive STEM learning companion for millions of students worldwide.
8. **Olympiad Publishing & Credentialing Authority:** Cryptographically verifiable proof-of-skill credentials recognized by global universities and employers.

</details>

<details>
<summary><strong>4. For Contributors, Academies &amp; Researchers</strong></summary>
<br />

Arithmo Edge welcomes collaboration across open-source engineering, Olympiad problem authoring, institutional onboarding, and AI reasoning research:

* **Open-Source Engineers:** Explore our federated repositories to contribute to `Arithmo-Core-SDK`, `KaTeX` rendering pipelines, `SymPy` verification modules, and client-side `WebGL`/`MediaPipe` performance optimizations.
* **Problem Authors & Olympiad Coaches:** Join Arithmo Forge to author seed problems, design procedural templates, and curate rated contest rounds.
* **Schools, Guilds & Coaching Academies:** Onboard your cohorts via Academy Arena to unlock Dual-Handle student management, automated problem sets, and private institutional leaderboards.
* **AI & Neuro-Symbolic Researchers:** Partner with our Zero-PII Reasoning Data Lake initiative to benchmark mathematical reasoning models against verified human solve distributions.

</details>

---

<div align="center">
  <h3>Build the Future of Competitive Mathematics</h3>
  <p>
    <a href="https://github.com/orgs/Arithmo-Edge/repositories"><strong>Explore Repositories</strong></a> &nbsp;•&nbsp;
    <a href="https://github.com/orgs/Arithmo-Edge/discussions"><strong>Join Discussions</strong></a> &nbsp;•&nbsp;
    <a href="https://arithmo-edge.github.io"><strong>Launch Core Portal</strong></a>
  </p>
  <p><sub>© Arithmo Edge (Powered by Olympiad Edge). Engineered for mathematical rigor at global scale.</sub></p>
  <hr />
  <p><strong>Authorized by Rayaan Tasnim</strong></p>
</div>
