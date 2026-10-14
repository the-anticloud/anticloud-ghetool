# Independent Insurance — GHETOOL

**Project:** GHETOOL  
**Category:** SOLAR  
**Upstream:** https://github.com/wouterpeere/GHEtool  
**Pinned commit:** `c18cebcc632fd324f7527dd758f1ed7efd980974`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `ac4d0f9ae48e5e0a2a725505b8a6fed634ee7b25f25d809b8811e446036c7db6`  
**Date:** October 2026

## Why AI-specific cover matters

Deploying AI in a regulated sector creates liability surfaces that ordinary
technology cover does not reach: inference liability, audit-trail liability,
data-breach liability and IP-infringement liability.

## How this project's architecture reduces insurable risk

| Risk | Cloud AI | GHETOOL with AIOSS |
|---|---|---|
| Audit-trail loss | high — vendor-controlled logs | low — append-only chain, verifiable offline |
| Data breach in transit | high — data transits external servers | low — no external endpoint |
| Compliance violation | high — cannot satisfy air-gap requirements | low — structural |
| IP liability | moderate | low — pinned provenance chain |

## Evidence package for an insurer

- AIOSS chain verification for head `ac4d0f9ae48e5e0a2a725505b8a6fed634ee7b25f25d809b8811e446036c7db6`
- The 16-check register with per-check evidence hashes
- Framework control mapping in `BENCH.json`

## Contact

lois@0-1.gg
