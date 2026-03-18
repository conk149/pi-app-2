PI Comparator (Offline, Client‑Side)
A browser‑based tool for pharmacists to compare 2–3 IV package inserts (PIs) side‑by‑side.
Runs entirely in the browser, supports PDF/TXT, and is designed for English‑language PIs.

Features
Local‑only processing

All parsing runs in the browser, no server.

Suitable for hospital or clinic PCs without backend deployment.

Upload & parsing

Drag‑and‑drop or file picker.

Accepts PDF (text‑based or scanned) and .txt files.

Text extraction for digital PDFs; OCR fallback planned for scanned PIs.

Clinical section comparison

Extracts and aligns key sections, e.g.:

Indications

Dilution / Reconstitution

Compatible diluents (NS, D5W, others)

Administration

Contraindications

Warnings / Precautions

Side effects / adverse reactions

Storage / stability

Shows each section per product with a “Key Differences” column.

Inspector tools

“Show extracted text” per file to QA parsing.

Export CSV for documentation or further analysis.

JSON export (optional) for feeding into external AI tools.

AI assistance hooks (optional)

UI button for “AI assist comparison”.

Intention: plug into local or API LLMs to summarise differences or answer clinical questions.

Core app works without any AI or network calls.

Why this exists
Package inserts vary a lot in wording and layout. Manually checking every section across 2–3 products is:

Time‑consuming at the clinical bench.

Error‑prone when headings differ (e.g. “Dilution” vs “Preparation for administration”).

This tool gives pharmacists a fast, visual diff across the key clinical sections while keeping everything local.

Getting started
Download or clone the repo.

Open pi app 2.html (or index.html if renamed) directly in a modern browser:

Chrome / Edge (recommended)

Firefox (works, but test with your PDFs)

Drag‑and‑drop 2–3 PIs into the upload area.

Click Process all files.

Scroll the comparison table:

Review each section side‑by‑side.

Use “Show extracted text” if anything looks off.

Click Export CSV to save a structured comparison.

No build step or server is required.

Intended workflow (pharmacist use)
Save PIs (PDF/TXT) from regulatory sites or hospital document system.

Open the comparator on a pharmacy PC or ward laptop.

Compare:

Different brands of the same molecule.

Old vs new version of the same product.

Originator vs generic.

Use the “Key Differences” and CSV to support:

DTC or formulary decisions.

Ward protocol updates.

Education and training.

Roadmap
Better robustness for global PI formats (EU SPC, HK, US PI).

OCR integration for image‑only scans (Tesseract.js in‑browser).

Configurable section lists (per institution or molecule type).

Pluggable AI assistance:

Local model mode (browser / on‑prem).

Remote API mode with institution‑controlled endpoint.

Light/dark themes and tablet‑friendly layout.

Limitations & disclaimers
Optimised for English‑language PIs.

Section detection is heuristic and may miss or mis‑align unusual layouts.

This tool does not replace clinical judgement, product monographs, or official labels.

Always verify critical details (dose, dilution, compatibility, contraindications, warnings) against the original PI.

Development notes
Single‑file HTML app (HTML + CSS + JavaScript in one file).

Uses PDF parsing in the browser for digital PDFs; OCR is planned but not required.

No external dependencies beyond browser‑loaded libraries (no Node/build pipeline).

