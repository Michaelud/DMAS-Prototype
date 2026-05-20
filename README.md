# DMAS — Disaster Multi-Agent Awareness System

A prototype implementation of the DMAS architecture proposed in:
> *"DMAS: A Multi-Agent System for Real-Time Disaster Situational Awareness"*
> Michael Michael Udofia, Computer Engineering, AkwaIbom, Nigeria.

## Overview
DMAS fuses heterogeneous data streams — social media posts, municipal
311/911 emergency calls, and IoT sensor data — through a coordinated
hierarchy of four specialized agents to produce a continuously updated
distress alert feed ranked by neighbourhood severity.

## Architecture
| Layer | Agent | Role |
|---|---|---|
| 1 | Ingestion Agent | Harvests weather, IoT, social media, 311 calls |
| 2 | Verification Agent | Computes Signal Credibility Score (Sc) |
| 3 | Synthesis Agent | Computes Composite Distress Severity Score (CDSS) |
| 4 | Deployment Agent | Ranks areas and allocates rescue resources |

## Files
- `dmas_lagos_flood_2024.py` — Scenario based on Lagos State flood, December 2024 (275,621 persons affected, IOM/NEMA, 2024)

## How to Run

### General prototype
```bash
pip install requests
python dmas_prototype.py --city Lagos
```

### Lagos 2024 flood scenario (no internet needed)
```bash
python dmas_lagos_flood_2024.py
```

## Key Results — Lagos 2024 Scenario
| Rank | Area | CDSS | Severity |
|---|---|---|---|
| 1 | Mile 12 / Owode | 0.889 | 🔴 CATASTROPHIC |
| 2 | Ajegunle | 0.879 | 🔴 CATASTROPHIC |
| 3 | Lagos Island | 0.854 | 🔴 CATASTROPHIC |
| 4 | Ikorodu | 0.849 | 🔴 CATASTROPHIC |
| 5 | Ketu | 0.752 | 🔴 CATASTROPHIC |
| 6 | Surulere | 0.612 | 🟠 CRITICAL |
| 7 | Lekki Phase 1 | 0.409 | 🟡 MODERATE |
| 8 | Victoria Island | 0.302 | 🟢 STABLE |

## Requirements
- Python 3.8+
- requests (`pip install requests`)
