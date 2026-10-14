# Technical Architecture — GHETOOL

**Upstream:** [https://github.com/arup-group/GHEtool](https://github.com/arup-group/GHEtool)
**License:** MIT
**Category:** SOLAR
**Anticloud Integration:** PAX L5 Narrow L2 General 27B + AIOSS + Offline-First

## Upstream Description

Ground heat exchange tool

## Anticloud Architectural Changes

1. PAX L5 Narrow L2 General 27B local irradiance forecasting — off-grid deployment
2. AIOSS tamper-evident energy production log per panel
3. AES-256 encryption for all inverter and grid data
4. Single-binary SCADA replacement deployable on Raspberry Pi at solar site
5. Zero-cloud: all forecasting, monitoring, and alerting runs locally
6. GPU/CPU equalizer: ML forecasting on edge CPU, scales to data center GPU
7. Offline weather data integration via local NWP model
8. Open Sunspec/Modbus integration replacing proprietary inverter software

## Integration Points

- **PAX Inference Socket:** Local HTTP endpoint at `127.0.0.1:11434/v1/chat` — same OpenAI-compatible API, zero cloud
- **AIOSS Hook:** Every write operation calls `aioss_append(event, payload)` before commit
- **Encryption Layer:** All file I/O routed through `anticloud_crypto.encrypt_at_rest()`
- **Single Binary Build:** `pyinstaller anticloud_ghetool.spec` or `go build -o ghetool`

## Deployment Modes

| Mode | Hardware | Notes |
| --- | --- | --- |
| Edge CPU | Raspberry Pi 4 / Intel NUC | Full feature set, PAX on CPU |
| Desktop GPU | RTX 3060 / A10 | PAX GPU inference, <1s latency |
| Server | 2× A100 | Full batch throughput |
| Air-gapped | Any x86/ARM | Zero network dependency |