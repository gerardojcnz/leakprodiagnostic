# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a single-file static landing page for **LeakPro Diagnostic**, a pool leak detection and repair company serving Miami-Dade, Broward, and Palm Beach counties in South Florida.

**Single file:** `docs/index.html` — contains all HTML, CSS, and JavaScript inline. No build tools, no dependencies, no package manager.

**To preview:** Open `docs/index.html` directly in a browser, or use Live Server in VS Code.

## Architecture

Everything lives in one file, organized in this order:

1. **CSS** (`<style>`) — CSS custom properties in `:root`, then sections in this order: animated background, nav, hero, section base, services grid, about split, process steps, testimonial, service areas, contact form, footer, scroll reveal, responsive breakpoints.
2. **HTML** (`<body>`) — fixed background layers → `<nav>` → `#services` → `#about` → testimonial strip → `#process` → `#contact` → `<footer>`.
3. **JavaScript** (inline `<script>`) — IntersectionObserver for `.reveal` scroll animations, nav background on scroll, form submit handler.

## Design System

CSS custom properties define the full palette — always use these variables, never raw hex values:

| Variable | Value | Use |
|---|---|---|
| `--navy` | `#071a2e` | Page background |
| `--deep` | `#0a2540` | Dark surfaces |
| `--mid` | `#133558` | Mid surfaces |
| `--water` | `#1a6fa8` | Water accent |
| `--aqua` | `#2fb8c6` | Primary accent / highlights |
| `--gold` | `#c8a96e` | CTAs, interactive elements |
| `--gold-light` | `#e6cfa3` | CTA hover states |
| `--glass` | `rgba(255,255,255,0.06)` | Card backgrounds |
| `--glass-border` | `rgba(255,255,255,0.12)` | Card borders |

**Fonts:** `Cormorant Garamond` (serif) for headings and display text — `DM Sans` (sans-serif) for body. Both loaded from Google Fonts.

## Key Patterns

**Scroll reveal:** Add class `reveal` to any element for fade-up-on-scroll. Use `reveal-delay-1` through `reveal-delay-4` to stagger siblings. The IntersectionObserver handles the rest.

**Nav logo:** The logo is an inline SVG (no external image file required) immediately followed by `.nav-logo-text` with `.nav-logo-name` and `.nav-logo-sub` spans.

**Service cards:** `.services-grid` uses `auto-fit minmax(260px, 1fr)`. Each `.service-card` has a decorative `.service-num` (large faded number) positioned bottom-right, and a top-border reveal animation on hover via `::before`.

**Contact form:** The `handleSubmit()` function is a simulated submission — it hides the form and shows `#form-success` after 1.2s. There is no real backend or email integration.

## Business Details (do not change without confirmation)

- Phone: `(305) 942-9447`
- Email: `info@leakprodiagnostic.com`
- Instagram: `@leakprodiagnostic`
- Service areas: Miami-Dade · Broward · West Palm Beach
