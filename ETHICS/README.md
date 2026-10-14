# Ethics — GHETOOL

**Project:** GHETOOL  
**Category:** SOLAR  
**Upstream:** https://github.com/wouterpeere/GHEtool  
**Pinned commit:** `c18cebcc632fd324f7527dd758f1ed7efd980974`  
**Assurance:** 16/16 checks passing  
**Ledger head:** `ac4d0f9ae48e5e0a2a725505b8a6fed634ee7b25f25d809b8811e446036c7db6`  
**Date:** October 2026

## Position

GHETOOL is packaged for offline deployment with a verifiable audit trail. The
ethical questions this raises are answered by making the system's behaviour
checkable rather than by policy statements.

## The four commitments

1. **No hidden egress.** The deployment has no external API dependency; this is
   testable by running it with the network disconnected.
2. **Attributable output.** Every artifact is recorded in a hash chain, so what
   the system produced can be reconstructed.
3. **Operator control.** The institution owns the hardware and the keys.
4. **Refusal to overclaim.** Where a certification is not held, the project says
   so rather than implying it.

## Dual use

This project is packaged for civilian and public-sector deployment. Where an
upstream has dual-use characteristics, the licence gate and the reference-only
marking in `BENCH.json` record that.
