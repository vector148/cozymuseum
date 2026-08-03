# 12. Zero-Clutter Root Directory

Date: 2026-08-03

## Status

Accepted

## Context

As the CozyMuseum project evolved, the root directory started accumulating various context documents, handoff notes, and utility scripts (e.g., `CONTEXT.md`, `HANDOFF.md`, and stray `.mjs` scripts). This clutter makes the repository harder for human developers to navigate and introduces noise when cross-platform AI agents attempt to discover canonical configuration files. A cluttered root directory violates modern repository hygiene standards.

## Decision

We will strictly enforce a "Zero-Clutter Root" policy across the repository:

1. **Root Directory Constraints:** The root directory MUST strictly contain ONLY files that are structurally mandatory for the framework/runtime (e.g., `package.json`, `vite.config.js`, `.env`), version control (`.gitignore`), and human onboarding (`README.md`, `LICENSE`, `CozyMuseum.bat`).
2. **AI Configurations & Context:** All AI-related context, rules, and configuration files MUST be stored in the `.agents/` workspace root.
3. **Scratchpads & Handoffs:** All planning documents, issue tracking, and manual handoff notes MUST be stored in `.scratch/`.
4. **Utility Scripts:** All ad-hoc or maintenance utility scripts MUST be stored in the `scripts/` directory.

## Consequences

- **Positive:** A cleaner, more professional repository structure that aligns with modern development standards.
- **Positive:** Faster and more accurate context loading for AI tools, as they are explicitly directed to `.agents/`.
- **Negative:** Requires strict discipline from both human developers and AI agents to consciously place new files in their appropriate designated subdirectories rather than dumping them at the root.
