# Educators — GHETOOL

**Project:** GHETOOL  
**Category:** SOLAR  
**Upstream:** https://github.com/wouterpeere/GHEtool  
**Pinned commit:** `c18cebcc632fd324f7527dd758f1ed7efd980974`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `ac4d0f9ae48e5e0a2a725505b8a6fed634ee7b25f25d809b8811e446036c7db6`  
**Date:** October 2026

## Teaching with GHETOOL

The project is usable as a worked example of offline-first packaging with a
cryptographic audit chain. It ships with the assurance suite, the evidence
register and the ledger, so students can verify claims rather than take them on
faith.

## Suggested exercises

1. Run `python tools/run_bench.py --out BENCH.json` and read the 16 results.
2. Recompute the SHA3-256 of a row's evidence file and compare to the register.
3. Walk the AIOSS chain from genesis to head `ac4d0f9ae48e5e0a2a725505b8a6fed634ee7b25f25d809b8811e446036c7db6` and confirm every link.
4. Break one artifact and observe the chain fail to verify.

## Licence for teaching

Apache 2.0 terms apply to academic and teaching use. See `24_ANTICOMMONS_LICENSE`.
