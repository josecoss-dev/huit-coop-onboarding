# HUIT Co-op Onboarding — Interactive Training Platform

**Harvard University Information Technology**  
Built by Jose Coss (joc5799) · IT Support Co-op · 2025

---

## Overview

A self-contained, interactive web-based training platform for incoming HUIT co-op students. Designed to replace static slide decks and passive orientation sessions with hands-on, scored learning modules that co-ops can complete on Day 1 before joining their respective teams.

Built to run entirely from GitHub Pages — no backend, no dependencies, no setup required for learners.

---

## Modules

| # | Module | Type | Est. Time |
|---|--------|------|-----------|
| 1 | What Is a Network? | Foundation | 5 min |
| 2 | Harvard's Network Environment (ClearPass, VLANs, SSIDs) | HUIT Context | 5 min |
| 3 | Finding Your MAC Address (macOS, Windows, iOS) | Hands-On | 5 min |
| 4 | Device Registration + Form Walkthrough + Practice Game | Hands-On + Game | 10 min |
| 5 | Real-World Troubleshooting Scenarios | Applied | 5 min |
| 6 | Knowledge Check Quiz (8 questions, auto-scored) | Assessment | 5 min |

**Total estimated time:** ~30 minutes

---

## Features

- **Interactive form walkthrough** — the actual ClearPass registration form with animated field-by-field explanations, color-coded field types (required / optional / VLAN), and progress dots
- **3-round practice game** — realistic scenarios (Art Museum, Lamont Library, Divinity School) where learners fill out the registration form and get scored on Description, Role, MAC Filter, and Resource Group
- **8-question auto-scored quiz** — answers lock on selection, correct answers reveal with explanations, final score card with feedback
- **Progress tracking** — nav bar tracks completion across all 6 modules
- **Harvard-specific content** — `getonline.harvard.edu`, `tools.noc.harvard.edu`, Aruba ClearPass, HCL vs Registered MAC filter, eduroam, Mobility Admin role

---

## Hosting

This platform runs as a single static HTML file via GitHub Pages.

```
https://pages.github.huit.harvard.edu/[org-or-user]/huit-coop-onboarding/
```

No build step required. The file is fully self-contained — fonts load from Google Fonts CDN, everything else is inline.

---

## File Structure

```
huit-coop-onboarding/
├── index.html          ← Networking 101 module (this file)
├── README.md           ← This file
```

Planned additions:
- `windows-basics.html` — Windows 11, Dell setup, domain join
- `office365.html` — Microsoft 365, Teams, SharePoint, OneDrive
- `harvard-systems.html` — ServiceNow, HarvardKey, VPN, printing

---

## Technical Details

- **Stack:** Pure HTML/CSS/JavaScript — zero frameworks, zero build tools
- **Fonts:** Inter (body) + JetBrains Mono (code/labels) via Google Fonts
- **Size:** ~60KB uncompressed
- **Browser support:** All modern browsers (Chrome, Firefox, Safari, Edge)
- **Offline capable:** After first load, works without internet (fonts cache)

---

## Content Coverage — Networking Module

### Harvard Network Infrastructure
- SSID breakdown: Harvard Secure, Harvard University (guest), eduroam
- Aruba ClearPass NAC: authentication, authorization, accounting, VLAN assignment
- Certificate-based Wi-Fi authentication via `getonline.harvard.edu`
- Wired Ethernet registration via `tools.noc.harvard.edu`

### ClearPass Registration Form Fields
| Field | Notes |
|-------|-------|
| MAC Address | Wi-Fi MAC for wireless, Ethernet MAC for wired — they differ |
| Owner | HarvardKey email or 8-digit HUID |
| Description | Device identity — e.g. "Tommy's End User Primary" |
| Role (Mobility) | VLAN assignment — majority of users: **Mobility Admin** |
| MAC Filter (Traditional) | **Registered** for most locations; **HCL** for Library |
| Resource Group | Department tag for documentation — Art Museum, Divinity, Lamont |
| Expiration | Contract end date for co-ops; 1 year for permanent staff |

### Troubleshooting Scenarios
- New hire with no certificate
- Device-specific registration (phone ≠ laptop)
- Expired annual registration (post-sabbatical)
- iOS Private Wi-Fi Address MAC rotation

---

## Maintained By

Jose Coss (`joc5799`) — HUIT IT Support Co-op  
Supporting: Art Museum · Divinity School · Lamont Library  
Contact: Jose_Coss@harvard.edu

