---
description: >-
  An unofficial command-line app that monitors Too Good To Go surprise bags,
  sends notifications, and optionally completes checkout.
hide:
  - toc
---

# TooGoodToGo Auto

**Monitor Too Good To Go surprise bags from the command line.**

Surprise bags sell out quickly. TooGoodToGo Auto is a personal helper tool:
it watches your favorite stores, sends a notification the instant an item
is available. It can automatically reserve and pay for it (including 3DS), so
you grab any item before it sells out. The app is free, open-source and runs on any platform.

[![Python 3.12+](https://img.shields.io/badge/Python-3.12%2B-3776AB.svg)](https://www.python.org/)
[![CI](https://github.com/miachillgood/toogoodtogo-auto/actions/workflows/ci.yml/badge.svg)](https://github.com/miachillgood/toogoodtogo-auto/actions/workflows/ci.yml)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://github.com/miachillgood/toogoodtogo-auto/blob/main/LICENSE)

![Demo of TooGoodToGo Auto in action](assets/demo.gif)

## Features

- **Account Login**: passwordless login and persistent sessions.
- **Automatic Checkout**: handles the full checkout flow including any 3DS challenges.
- **Easy Setup**: all settings in a single file, editable with any text editor or directly from the command line - no extra tools needed.
- **Interactive Menu**: guided flow, easy to navigate.
- **Mobile & Desktop Notifications**: get notified via Ntfy when monitored items become available.
- **Monitor Items**: watch any item in your area and wait for it to become available.

## Get started

<div class="grid cards" markdown>

- **[Installation](installation.md)**

    Install with `uv` or `pipx`.

- **[Quick Start](quickstart.md)**

    From zero to monitoring in a few steps.

- **[Configuration](configuration.md)**

    Every setting explained in detail.

- **[FAQ](faq.md)**

    Common questions and troubleshooting.

</div>

!!! warning
    This project is an unofficial, independent third-party tool and is **not
    affiliated with Too Good To Go**. Use of this tool may violate the Too
    Good To Go Terms of Service. See the [Disclaimer](disclaimer.md) for
    details.
