# Bullet Forge

A browser-based writing-assistance tool for Air Force performance statements (EPB/OPB), decorations, and award (1206) packages.

**Live site:** `https://YOUR-USERNAME.github.io/bullet-forge/`

---

## What it does

- **1206 / Award statements** — evidence-based scoring, line-fit shaping, verb tiering, recognition and metric analysis.
- **Evaluations (DAF 910/911)** — member info with format checking, the four Major Performance Areas, Higher Level Reviewer, Future Roles, fitness statement, and rating chain; prints a draft that matches the MyEval layout (Courier, 98 characters per line).
- **Decorations** — citation drafting with the character window and a certificate line-layout preview that warns before text overruns the signature block.
- **Proofing** — consistency review (ampersand vs. "and", repeated verbs, overused words), a shorthand translator that converts old bullet abbreviations into narrative statement language, an in-place thesaurus, and an advisory proficiency read.

## How it's built

- **A single self-contained HTML file.** No build step, no framework, no package dependencies.
- **Runs entirely client-side** in the browser. There is **no backend server** and **no database**.
- **Loads no external code** — no content delivery network, no third-party scripts.
- **All working data stays in the local browser** (browser storage). Nothing is uploaded anywhere.

### Network behavior (full disclosure)

| Call | Purpose | Data sent |
|---|---|---|
| `api.datamuse.com` | Optional thesaurus lookup | A single dictionary word. Never names, never statement content. |

That is the **only** outbound connection the tool makes. If it is blocked, the thesaurus simply returns nothing and every other function continues to work. An offline build with this call removed — making **zero** outbound connections — is available on request.

## Data handling

- No accounts, no logins, no telemetry, no analytics.
- No Protected Health Information, Personally Identifiable Information, or Controlled Unclassified Information is transmitted off the workstation.
- Users are directed **not** to enter Protected Health Information.
- The bundled reference libraries are **anonymized**: personal names and identification numbers have been removed and verified.

## Reviewing the source

The entire application is the single `index.html` file in this repository — readable end to end, no minification or obfuscation. Cybersecurity reviewers can inspect exactly what it does without running it.

## Status

Locally developed and maintained. Provided as-is, with no warranty. Not an official Department of Defense or Air Force application; the views and content are the author's and do not represent DoD or its components. Governing publications control: DAFI 36-2406 (evaluations) and AFMAN 36-2806 (awards and decorations).
