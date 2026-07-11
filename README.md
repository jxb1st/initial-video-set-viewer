# Initial Video Set — Diverse Cross-Benchmark Sample

A self-contained static viewer for a **46-video initial set** sampled across all four target
benchmarks. Single `index.html` (all metadata inlined) + `videos/` (compressed 360p clips,
HTTP-Range friendly for seeking). `manifest.json` / `summary.md` carry the full per-video tags.

## What this is

A **stratified** seed set (not random): videos were picked to spread coverage across a set of
diversity dimensions so the set is **not cooking-only and not manipulation-only**.

## Selection dimensions

**Primary (drive the quota):**
- **A · Source benchmark** — mix all 4 targets; no dataset dominates.
- **B · Event / scenario type** — the anti-"only cooking / only manipulation" axis:
  procedural-task · instructional-demo · excursion-travel · sport-performance · social-event ·
  shopping-errand · daily-routine. Every bucket has a floor of coverage.
- **C · Task / interaction form** — proactive-assist / conversational-QA / long-MCQ /
  procedural-manipulation / instructional-tutorial / unconstrained-egocentric.
- **D · Temporal scale** — short (<100s) / medium (100–250s) / long (>250s).

**Secondary (recorded, heuristic):** E · Viewpoint (ego/exo) · F · Environment
(indoor-stationary / outdoor-locomotion) · G · Hand-object interaction intensity.

Sources with clean labels (Wearable-AI) were stratified from their own metadata; sources with no
on-disk labels (HowTo100M, EgoSchema) were tagged by a 1-frame Gemini-flash activity classification
then diversified; CaptainCook4D is 100% cooking so it is capped at 6 distinct recipes.

## Source benchmarks (where the raw videos come from)

| Source | # | Paper / origin | What the raw video is |
|---|---|---|---|
| Wearable-AI | 30 | Wearable AI Workshop @ ECCV 2026 (`facebook/wearable-ai`) | Meta-collected egocentric wearable-camera everyday-activity videos (val-only, 700/task) |
| CaptainCook4D | 6 | CaptainCook4D (NeurIPS 2024 D&B) | Egocentric GoPro cooking sessions with step/error annotations |
| HowTo100M | 5 | HowTo100M (ICCV 2019) | Exocentric narrated instructional YouTube videos |
| EgoSchema | 5 | EgoSchema (NeurIPS 2023, from Ego4D) | Egocentric ~3-min unconstrained daily-activity clips |

## Composition (46 videos)

- **Source:** Wearable-AI 30 · CaptainCook4D 6 · HowTo100M 5 · EgoSchema 5
- **Event type:** procedural-task 23 · instructional-demo 6 · excursion-travel 5 · daily-routine 4 ·
  sport-performance 3 · social-event 3 · shopping-errand 2
- **Task form:** proactive-assist 10 · conversational-QA 10 · long-MCQ 10 · procedural-manipulation 6 ·
  instructional-tutorial 5 · unconstrained-egocentric 5
- **Temporal scale:** long 23 · medium 15 · short 8

Each card in the viewer shows the player + all dimension tags + its source provenance
(dataset, track, original video id, duration). Filter chips at the top narrow by any axis.
