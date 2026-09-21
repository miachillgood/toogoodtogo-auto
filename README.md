[![CI](https://github.com/miachillgood/toogoodtogo-auto/actions/workflows/ci.yml/badge.svg)](https://github.com/miachillgood/toogoodtogo-auto/actions/workflows/ci.yml)
[![Python 3.12+](https://img.shields.io/badge/Python-3.12%2B-3776AB.svg)](https://www.python.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

# TooGoodToGo Auto

TooGoodToGo Auto is an unofficial Python command-line application for finding,
monitoring, and reserving Too Good To Go surprise bags. It supports passwordless
email login, persistent sessions, configurable search areas, ntfy notifications,
and optional checkout with 3-D Secure handling.

> [!IMPORTANT]
> This project uses unofficial endpoints. They can change without notice, and
> using automation may violate Too Good To Go's terms or lead to rate limits or
> account restrictions. Start with checkout disabled and use the software at
> your own risk.

## Features

- Passwordless account login with a six-digit email code
- Search by latitude, longitude, and radius
- Filters for favourites, availability, and store name
- Continuous monitoring with configurable hours and polling interval
- Desktop and mobile notifications through [ntfy](https://ntfy.sh/)
- Optional automatic checkout and support for common 3-D Secure flows
- Local configuration, session persistence, and payment-field validation

## Install from this repository

Python 3.12 or newer is required. The recommended installation method is
[uv](https://docs.astral.sh/uv/):

```bash
git clone https://github.com/miachillgood/toogoodtogo-auto.git
cd toogoodtogo-auto
uv tool install .
```

For development:

```bash
git clone https://github.com/miachillgood/toogoodtogo-auto.git
cd toogoodtogo-auto
uv sync
uv run tgtg-auto
```

You can launch the installed application with `tgtg-auto`. The compatible
aliases `tgtg`, `tgtg-cli`, `toogoodtogo`, and `toogoodtogo-cli` are also
available.

## Quick start

1. Run `tgtg-auto`.
2. Choose **Settings**. The generated `settings.ini` opens in your editor.
3. Enter your account email, coordinates, and search radius.
4. Leave `ENABLE_CHECKOUT = False` during initial setup.
5. Restart the application, select **Login**, and enter the email code.
6. Select **Monitor**, choose a bag, and keep the process running.

The full settings reference is in
[docs/configuration.md](docs/configuration.md). Installation details and
troubleshooting are in the [docs](docs/) directory.

## Checkout and external services

Checkout is opt-in. Enabling it requires payment-card fields in the local
settings file. Depending on the issuer, a 3-D Secure confirmation may still be
required on another device.

Some anti-bot and checkout cryptography flows inherited from the upstream
implementation call services hosted at `peterschwps.com`. These calls occur
when the related login protection or checkout flow is triggered. Review
`src/tgtg_cli/apis/tgtg.py` and `src/tgtg_cli/apis/cryptography.py` before using
automatic checkout if this dependency is not acceptable for your environment.

Do not commit `settings.ini`, session files, card details, tokens, cookies, or
logs. Runtime data is stored in the platform-specific user configuration and
cache directories rather than inside the repository.

## Development

```bash
uv sync
uv run ruff check .
uv run pytest
uv build
```

Continuous integration runs linting and the test suite on Python 3.12, 3.13,
and 3.14 across Linux, macOS, and Windows.

## Attribution

This repository is adapted from
[peterschwps/TooGoodToGo-CLI](https://github.com/peterschwps/TooGoodToGo-CLI).
The original copyright notice is retained under the MIT License; see
[NOTICE.md](NOTICE.md) and [LICENSE](LICENSE).

## Disclaimer

This project is an independent third-party tool. It is not affiliated with,
endorsed by, sponsored by, or officially connected to Too Good To Go ApS or
its subsidiaries. "Too Good To Go" and "TGTG" are trademarks of Too Good To Go
ApS and are used only to identify the service with which this software
interacts.

The software is provided without warranty. You are responsible for reviewing
the service terms, local laws, account risk, orders, and payments before use.
