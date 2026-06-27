# ClawIndex Dashboard — Agent Guidance

## What This Is

ClawIndex is durable, vendor-neutral, OpenTelemetry-first observability for an operator's own agent fleet — the durable system-of-record that Aspire (ephemeral by design) is not.

This repo is a static vanilla-JS/HTML dashboard with no build step. It deploys to Cloudflare Pages.

## Surfaces

**`demo/`** — concept preview using seeded, simulated data. This surface must stay clearly labeled as a concept preview at all times.

**`live/`** — live view that reads real data from the collector's read API. The live view must render only data the collector can truthfully produce. No seeded or simulated values here.

## Core Constraints

**No cross-tenant data.** All comparisons and rollups are scoped to a single operator's own boundary — their own agents, orgs, and business units. Never build anything that reads or compares across tenant boundaries.

**Claims discipline.** Do not state or imply product capabilities that are not actually live. Honest framing over impressive framing.

**Open core.** This repo is licensed under AGPL-3.0. A separate proprietary managed tier exists. Never reference or copy private/managed-tier code into this repo.

## Workflow

- Branch off `main` for all work.
- Never commit to `main` directly.
