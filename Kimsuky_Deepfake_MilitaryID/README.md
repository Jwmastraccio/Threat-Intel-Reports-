# Kimsuky – Deepfake Military ID (2025)

## Executive Summary
- North Korean group **Kimsuky** used **deepfake military ID** images to spear-phish South Korean defense orgs.
- Lure leads to user execution (attachments/links) and **AutoIt/batch**-based evasion.
- This folder provides a concise intel package: **report**, **IOCs (CSV & STIX)**, **ATT&CK mapping**, and **detections**.

## What’s Here
- [`sources.md`](./sources.md) – key references
- [`iocs.csv`](./iocs.csv) – normalized, SIEM-ready
- [`stix2_bundle.json`](./stix2_bundle.json) – generated from CSV
- [`attack_navigator_layer.json`](./attack_navigator_layer.json) + [`figures/attack_heatmap.png`](./figures/attack_heatmap.png)
- [`detections/sigma/`](./detections/sigma/) – starter Sigma rule

## Key TTPs (ATT&CK)
- T1566.001 / .002 – Spearphishing (attachment/link)
- T1204 – User Execution
- T1027 – Obfuscated/Compressed Files and Info
- T1059 – Command & Scripting Interpreter (AutoIt/batch)

## How to Use
- Import `iocs.csv` into your SIEM/EDR (columns documented in the CSV header).
- Open `attack_navigator_layer.json` in **ATT&CK Navigator** (Import → Upload).
- Use Sigma rules as a starting point for detection engineering (Sysmon/WEC/SIEM backends).

## Campains
- [Kimsuky Deepfake Military ID Campaign](./Kimsuky_Deepfake_MilitaryID/README.md)
  - [IOCs (CSV)](./Kimsuky_Deepfake_MilitaryID/iocs.csv)
  - [STIX 2.1 bundle](./Kimsuky_Deepfake_MilitaryID/stix2_bundle.json)
  - [ATT&CK layer](./Kimsuky_Deepfake_MilitaryID/attack_navigator_layer.json)
  - [Sigma rules](./Kimsuky_Deepfake_MilitaryID/detections/sigma/)

## Attribution Confidence
- **Medium** — consistent with public reporting and historical Kimsuky TTPs; some indicators generalized.
