# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A single-file static HTML page that displays an Orthodox Christian prayer (the Jesus Prayer) with an icon and countdown timer before internet browsing. Designed as a voluntary friction tool that integrates with iOS Shortcuts automation. Deployed via GitHub Pages.

## Development

There is no build process, test suite, or linting configuration. The entire application is a single `index.html` file with embedded CSS and JavaScript.

**To preview:** Open `index.html` in any browser.

**To deploy:** Push to `main` branch; GitHub Pages serves from root.

## Architecture

`index.html` contains three embedded layers:

- **CSS (lines ~14-196):** Dark liturgical theme using EB Garamond (Google Fonts). Staggered `fadeIn` animations for icon, prayer, and timer. Responsive layout using flexbox and `100dvh`. Includes a CSS fallback cross if the icon image fails to load.
- **HTML (lines ~199-237):** Three sections — icon frame, prayer text, and timer/button.
- **JavaScript (lines ~239-276):** Countdown timer controlled by `WAIT_SECONDS` (default 15). On completion, attempts `window.close()` with a fallback message for iOS where `close()` is restricted.

## Key Customization Points

- `WAIT_SECONDS` constant in the `<script>` block controls the countdown duration
- Icon image URL in the `<img>` tag (defaults to Wikimedia Commons Christ Pantocrator)
- Prayer text in `.prayer-text` element
- Instruction text in `.instruction` element

## External Dependencies

- Google Fonts: EB Garamond (loaded via `<link>`)
- Wikimedia Commons: default icon image (public domain)
