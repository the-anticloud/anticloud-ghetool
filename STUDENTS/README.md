# Students — GHETOOL

**Project:** GHETOOL  
**Category:** SOLAR  
**Upstream:** https://github.com/wouterpeere/GHEtool  
**Pinned commit:** `c18cebcc632fd324f7527dd758f1ed7efd980974`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `ac4d0f9ae48e5e0a2a725505b8a6fed634ee7b25f25d809b8811e446036c7db6`  
**Date:** October 2026

## What this project gives you

A complete worked example of offline-first packaging with a cryptographic audit
chain: source pinned at `c18cebcc632fd324f7527dd758f1ed7efd980974`, a 16-check assurance suite, an evidence register
with per-check hashes, and an AIOSS ledger chain ending at `ac4d0f9ae48e5e0a2a725505b8a6fed634ee7b25f25d809b8811e446036c7db6`.

## Learn by verifying

```
python tools/run_bench.py --out BENCH.json
```

Then take any row from `ISOLATED_LAB_RESULTS/03_Result_Register.md`, recompute
the SHA3-256 of its evidence file, and confirm it matches. If it does not match,
the record has been altered — that is the whole point of the chain.

## Licence

Apache 2.0 terms apply to study and teaching use.
