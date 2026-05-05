# Ark HCG-50K · Screen Wireframes

Wireframes for the 7" touchscreen UI on the Ark HCG-50K chlorine generator.

- **Resolution:** 1024 × 600 px
- **Display:** 7" IPS (DaCai DC10600AM070, RS232/TTL serial)
- **Design language:** Industrial HMI — glanceable from 4 ft, equipment-bay deployment
- **Reference vibe:** Cummins generator HMIs · Tesla wall connectors · marine plotters

## Live Preview

View the gallery: **[index.html](./screens/index.html)** (after enabling GitHub Pages, the live URL will be at `https://<username>.github.io/<repo>/screens/index.html`)

## Screens

### v2 · Industrial HMI (recommended direction)

| Screen | File | Notes |
|---|---|---|
| Home — Running (Dark) | `screens/home-v2.html` | Pool ORP hero with 24h sparkline trace, green status bar |
| Home — Running (Light) | `screens/home-v2-light.html` | Sun-readable variant |
| Home — Salt Low (Warning) | `screens/home-v2-alarm.html` | Yellow status bar, salt card highlighted |
| Home — Leak Detected (Fault) | `screens/home-v2-fault.html` | Red status bar, all sensors dimmed |
| ORP Detail · Drill-down | `screens/orp-detail.html` | Live "orbing" value, full 24h history graph, calibrate access |
| Setup · Set ORP Target | `screens/setup-target.html` | Onboarding wizard, step 3 of 5 |

### v1 · Earlier iterations (archive)

Original 6-tile dashboard layouts kept for comparison. See gallery.

## Color System

| Token | Dark | Light | Use |
|---|---|---|---|
| HASA orange | `#EB8B23` | `#EB8B23` | Brand mark, sparkline trace, primary action |
| Status green | `#00C853` | `#00A040` | Running |
| Status yellow | `#FFAB00` | `#C77700` | Attention / warning |
| Status red | `#D50000` | `#C20018` | Fault / shutdown |

Status colors follow traffic-light convention. HASA orange is reserved for the brand and primary actions — never for status communication.

## Editing

These are static HTML files with inline CSS. To edit:

1. Clone the repo: `git clone <repo-url>`
2. Open any file in your editor
3. Open the file in a browser to preview
4. Or run a local server: `python3 -m http.server 8093 --directory .` and visit `http://localhost:8093/screens/index.html`

No build step, no dependencies. Just HTML + CSS + a tiny bit of inline JS for iframe scaling in the gallery.

## Hardware context

| Component | Spec |
|---|---|
| MCU | ESP32-S3WN8 |
| Display interface | RS232/TTL serial (HMI_RX/TX on GPIO17/18) |
| Sensors | RS-485 Modbus RTU via DIEWU 1-to-8 hub |
| Connectivity | WiFi (built-in), Ethernet (W5500), LTE (IoTNext GEN2) |
| Cloud | AWS IoT MQTT |

See the design system in any of the screen files — all CSS is inline and self-documenting.
