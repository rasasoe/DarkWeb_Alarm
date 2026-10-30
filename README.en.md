# DOTAS v1.3 — Dark-Web OSINT Threat Alert System

<div align="center">
  <p><a href="README.md">🇰🇷 한국어</a> · <strong>🇺🇸 English</strong></p>
</div>


<div align="center">

![Python](https://img.shields.io/badge/Python-3.9%2B-3776AB?logo=python&logoColor=white)
![OSINT](https://img.shields.io/badge/Focus-OSINT%20%2F%20CTI-64748B)
![Tor](https://img.shields.io/badge/Tor-Optional%20Proxy-7D4698)
![Alerts](https://img.shields.io/badge/Alerts-Telegram-229ED9?logo=telegram&logoColor=white)

**A lightweight OSINT collection and threat-indicator alert prototype.**
</div>

## What it does

The original DOTAS project describes gathering public threat-related references from configured clearnet sources and optional Tor-accessible index/directory sources, extracting simple indicators, and issuing notifications.

| Pipeline stage | Function |
| --- | --- |
| Public-source collection | HTTP and optional configured Tor SOCKS proxy |
| Text processing | HTML extraction and keyword-based filtering |
| IOC candidate extraction | Simple domain/email expressions |
| Deduplication | Locally records already-seen indicators |
| Reporting and alerts | CSV output and optional Telegram bot messages |

```mermaid
flowchart LR
  SRC["Public OSINT / Optional Onion Index"] --> COL["Collector"]
  COL --> TEXT["Text Normalization"]
  TEXT --> IOC["IOC Candidates"]
  IOC --> DEDUP["Seen Indicator Check"]
  DEDUP --> OUT["CSV / Optional Telegram Alerts"]
```

## Scope and limitations

- **Publicly reachable sources only:** do not collect stolen credentials, private data or unapproved systems.
- **Tor is not absolute anonymity:** transport configuration can reduce certain forms of exposure but does not guarantee safety or privacy.
- **IOC extraction is a candidate signal:** a regex match is not proof of compromise or a reliable threat classification.
- This README reflects the documented prototype capabilities; it is **not** a claim of fresh live-source validation.

## Getting started

See the **[original Korean README](README.md)** for the exact dependencies, source configuration, Tor SOCKS settings (if used), notification setup, sample logs, and troubleshooting.

## Related CTI work

The newer [DotasPlus](https://github.com/rasasoe/DotasPlus) repository explores a more structured document → IOC → protected asset → incident pipeline. These are separate projects with different scopes.

---

*DOTAS · OSINT / Threat Intelligence · Prototype*
