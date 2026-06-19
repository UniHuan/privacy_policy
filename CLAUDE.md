# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

Static HTML hosting repository for privacy policies and terms of service of UniHuan's iOS apps. Each app gets a self-contained HTML page that serves as its App Store privacy policy link.

## Products

| File | App | Description |
|------|-----|-------------|
| `SolarTermsWellness.html` | 四时养 SiShiYang | TCM seasonal wellness app |
| `chengyudian.html` | 成语典 ChengYuDian | Chinese idiom learning app |
| `shiyun.html` | 诗韵 ShiYun | Chinese poetry app |
| `legal/privacy.md` | 出海合规通 ChuHaiHeGuiTong | Trade compliance app |
| `legal/terms.md` | 出海合规通 ChuHaiHeGuiTong | Terms of service |

## Architecture

- **No build step, no dependencies.** Every HTML file is self-contained — CSS is inline in `<style>` tags, no external resources.
- **Template pattern:** CSS variables for colors → mobile-first responsive (max-width: 720px) → card-based sections → Chinese system fonts (`-apple-system, "PingFang SC"`).
- **Per-app branding:** Each app uses its own primary color variable (`--primary`) and icon.
- **Common sections:** data collection → non-collected data → usage → storage/security → user rights → children's privacy → policy updates → contact.

## Conventions

- Privacy policy content is in standalone HTML (apps 四时养/成语典/诗韵); terms of service use Markdown (出海合规通).
- All dates use Chinese format: `2026年6月19日`.
- Contact email across all apps: `huanyurui_innovation@outlook.com`.
- Apps are all "no registration, data-local-first" — emphasize this in privacy policies.
- Adding a new app: copy the nearest matching HTML template, adjust brand colors and app-specific data handling details.

## Hosting

These files are served as static pages (GitHub Pages). After pushing, the privacy policy URL follows the pattern:
`https://unihuan.github.io/privacy_policy/<filename>.html`
