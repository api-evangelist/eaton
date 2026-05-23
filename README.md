# Eaton

Eaton Corporation plc (NYSE: ETN) is a global intelligent power-management company spanning electrical, aerospace, vehicle, and eMobility segments. Its public digital surface centers on the **Brightlayer** portfolio — software suites for Data Centers, Utilities, Industrial, Buildings, and Mobility — together with a developer program at [developer.eaton.com](https://developer.eaton.com/get-started) and an API Specification Catalog on the [for-developer-partners portal](https://www.eaton.com/us/en-us/digital/for-developer-partners/API_Specification_Catalog.html).

The most fully documented developer-facing surfaces today are:

- **Eaton Smart Breaker API** (`api.em.eaton.com`, formerly the EM API) — commission, monitor, and control Eaton AbleEdge smart breakers and Green Motion EV smart-breaker chargers (`hardwareType: emcb | ev-emcb`).
- **Brightlayer Demand Response Service API** — utility-grade load-control orchestration for Eaton DRMS programs.
- **Smart Ambient Monitoring API** — healthcare-targeted AI/ML inference over smart-breaker energy data, sold via the Brightlayer Experience Hub.
- **Brightlayer Operations Insight APIs** — connect partner / customer apps to the Brightlayer monitoring & management service.
- **Brightlayer RESTful API (On-Premise, 8.0)** — REST surface of the on-premise Brightlayer Power / Distributed IT / DCIM / EPMS suite.
- **Eaton Rack PDU G4 REST API** — NMC-exposed REST for outlet control, telemetry, and environmental sensors.
- **CI-Data Open API (by WES)** — partner-listed EPMS data API on the Brightlayer Experience Hub.
- **Eaton easyE4 JSON API** — JSON-over-HTTP API on the easyE4 PLC / control relay.
- **Brightlayer UI** — open-source React / Angular / React Native design system at [github.com/brightlayer-ui](https://github.com/brightlayer-ui).

Eaton's AI strategy is anchored by two major partnerships: the **Beam Rubin DSX platform** with NVIDIA (announced March 2026) — a reference architecture for 800 VDC AI factories on NVIDIA's Vera Rubin platform — and the **Brightlayer Digital Energy Twin** with Autodesk (Tandem-integrated AI digital twin for buildings and data centers).

## Artifacts in this repo

| Folder | Contents |
|---|---|
| `apis.yml` | Top-level API Evangelist index (12 APIs / surfaces, common properties, marketplace, developer portal, etc.) |
| `openapi/` | `smart-breaker-openapi.yml` — reconstructed OpenAPI 3.0 spec for the Eaton Smart Breaker / EV Charger API (auth, devices, commands, telemetry, sessions, events). |
| `capabilities/` | Naftiko capability files for Smart Breaker, EV Charging, Demand Response, Ambient Monitoring, plus shared cross-API primitives. |
| `json-schema/` | JSON Schemas for Device, EnergyReading, ChargingSession, DeviceEvent. |
| `json-structure/` | Hierarchical org → location → device structure for the Smart Breaker API. |
| `json-ld/` | `eaton-context.jsonld` — schema.org-aligned JSON-LD context for Eaton Brightlayer concepts. |
| `examples/` | Request/response examples: OAuth token, list devices, send command, energy telemetry, EV sessions. |
| `rules/` | `smart-breaker-rules.yml` — Spectral ruleset enforcing Eaton-specific conventions (subscription key header, hardware-type enum, EV-Only tagging). |
| `vocabulary/` | `eaton-vocabulary.yml` — products, APIs, terms, partnerships, segments, tags. |
| `plans/` | `eaton-plans-pricing.yml` — Brightlayer 8.0 tier-free model and per-API subscription gating (API Commons Plans 0.1). |
| `rate-limits/` | `eaton-rate-limits.yml` — documented + inferred limits across EM API, DRMS, and on-premise Brightlayer (API Commons Rate Limits 0.1). |
| `finops/` | `eaton-finops.yml` — FOCUS-aligned billing surface for Brightlayer Experience Hub + partner pass-through. |

## Key references

- [Brightlayer overview](https://www.eaton.com/us/en-us/digital/brightlayer.html)
- [Brightlayer Experience Hub](https://www.eaton.com/us/en-us/digital/brightlayer-experience-hub.html) — marketplace at [eaton.byappdirect.com](https://eaton.byappdirect.com/)
- [Eaton developer portal](https://developer.eaton.com/get-started) and [API Specification Catalog](https://www.eaton.com/us/en-us/digital/for-developer-partners/API_Specification_Catalog.html)
- [Smart Breaker API docs](https://api.em.eaton.com/docs) and [preview docs](https://api.em.eaton.com/preview/docs)
- [AbleEdge Smart Breaker Developer Portal](https://ableedge-portal.eaton.com/) / [portal.em.eaton.com](https://portal.em.eaton.com/)
- [Brightlayer RESTful API User Guide v8 (PDF, Oct 2025)](https://www.eaton.com/content/dam/eaton/products/brightlayer/brightlayer-power/eaton-brightlayer-restful-api-user-guide-v8.pdf)
- [Brightlayer 8.0 release notes blog](https://www.eaton.com/us/en-us/company/news-insights/blog/brightlayer-8-0-release-whatsnew.html)
- [Eaton + NVIDIA Beam Rubin DSX press release (Mar 2026)](https://www.eaton.com/us/en-us/company/news-insights/news-releases/2026/eaton-collaborates-with-nvidia-to-unveil-its-beam-rubin-dsx-platform.html)
- [Eaton + Autodesk Digital Energy Twin press release (Sep 2025)](https://www.eaton.com/us/en-us/company/news-insights/news-releases/2025/eaton-collaborates-with-autodesk-to-accelerate-building-digitalization.html)
- [Brightlayer UI on GitHub](https://github.com/brightlayer-ui)

## Notable absences

- No public, unauthenticated OpenAPI / Swagger JSON endpoint is reachable for `api.em.eaton.com` — the OpenAPI in `openapi/` is reconstructed from the public docs portal and is labelled as such (`x-spec-status: reconstructed-from-public-docs`).
- No public pricing for Brightlayer suites or per-API subscriptions; the Brightlayer 8.0 model is described as "tier-free" but rates are negotiated, not published.
- No public-facing status page for `api.em.eaton.com`.
- No public RSS / Atom feed for Brightlayer release notes — only the press-release and blog pages.
- The `brightlayer-ui` GitHub org's active repos collapsed to just the docs site and `.github`; the per-framework packages were consolidated into a monorepo (most legacy repos are now archived with a "This repo has moved" notice).
