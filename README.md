# clawindex-dashboard

Concept and economics-view surface for ClawIndex. Part of the ClawIndex open core (AGPL-3.0).

**Status: early.** Under active development.

## What this is — and what it is not

ClawIndex does NOT ship a custom SRE/span dashboard. ClawIndex is a standards-correct OTLP backend; operators view spans, traces, and operational health in whatever OTLP-compatible viewer they already run (Grafana, Aspire, Jaeger, and so on). Building a bespoke span renderer would reinvent, worse, what the OpenTelemetry ecosystem already provides.

This repository is therefore narrow on purpose. It holds:

- `demo/` — a concept preview, using seeded/simulated data, that illustrates the ClawIndex economics-and-accountability view. It is clearly labeled as a concept and is not a live product.
- `live/` — reserved for the custom economics/accountability surface: cost attribution, spend on unnecessary escalations, bottleneck and underperformance accountability, and trends over time. This is the one surface generic OTLP viewers do not provide, because it requires ClawIndex's pricing matrix, baselines, and derived analytics. It may begin as exports/reports before becoming interactive.

## What this repo is not for

- Not an SRE/operational span dashboard. Point your existing OTLP viewer at the collector for that.
- Not a re-implementation of trace/span timelines, fleet health tables, or live span views. The ecosystem renders those.

## Design constraints

- Static frontend, no build step. Deploys to Cloudflare Pages.
- The concept demo stays clearly labeled as seeded/concept at all times.
- The live economics surface renders only data the collector and economics layer can truthfully produce — no seeded values presented as real, no cross-tenant comparison. All analysis is intra-tenant.
- Claims discipline: do not state or imply capabilities that are not live. Honest framing over impressive framing.

## License

AGPL-3.0. Copyright Range Point AI, 2026. See [LICENSE](LICENSE).

The hosted economics/accountability layer is a separate proprietary managed tier. This open-core repository never depends on or references it.
