# Build and Test

**Project:** `GHETOOL`
**Upstream:** https://github.com/arup-group/GHEtool
**License:** MIT

## Quick Start

```bash
git clone https://github.com/arup-group/GHEtool
cd GHEtool
pip install -r requirements-anticloud.txt
python anticloud_main.py --offline --pax-local
```

## Anticloud Improvements Applied

1. PAX L5 Narrow L2 General 27B local irradiance forecasting — off-grid deployment
2. AIOSS tamper-evident energy production log per panel
3. AES-256 encryption for all inverter and grid data
4. Single-binary SCADA replacement deployable on Raspberry Pi at solar site
5. Zero-cloud: all forecasting, monitoring, and alerting runs locally
6. GPU/CPU equalizer: ML forecasting on edge CPU, scales to data center GPU
7. Offline weather data integration via local NWP model
8. Open Sunspec/Modbus integration replacing proprietary inverter software

## Benchmark Targets

| Metric | Target |
| --- | --- |
| Latency | Primary inference task: <5s on CPU, <1s on GPU |
| Throughput | Batch processing: >100 items/hour on single CPU server |
| Memory | <8GB RAM for standard deployment |
| Accuracy | Task-specific accuracy within 5% of cloud-API baseline |

## Build Status

Not yet measured. Run verified build and record actual figures above.
