# Agent instructions

## Purpose

Maintain this repository as the source archive for the custom ChatGPT Pets in `pets/`. Preserve each pet's identity and keep its final sprite sheet, source artwork, previews, and QA reports together.

## Repository and push destination

- GitHub repository: <https://github.com/Akshaysehgal2005/codex-custom-pets>
- Remote: `origin` (`https://github.com/Akshaysehgal2005/codex-custom-pets.git`)
- Default branch: `main`
- Push completed repository changes to `origin/main`. Do not force-push or rewrite history.
- This repository is public. Do not commit credentials, upload-session IDs, expiring media URLs, private user data, or unrequested reference material.

## Layout

- `pets/<slug>/spritesheet-extended.png`: exact final v2 sheet.
- `pets/<slug>/source/`: canonical base, generated source strips, and references approved for this repository.
- `pets/<slug>/previews/`: contact sheets, per-state GIFs, direction loop, and MP4.
- `pets/<slug>/qa/`: structural validation and quality reports.
- `images/<slug>.png`: transparent idle-pose portraits used in the root README.
- `skills/create-pet/`: backup snapshot of the `work-pets:create-pet` skill and its bundled scripts.
- `skills/references/`: shared contract documents required by the backed-up skill.

Keep each pet in its own folder. Use lowercase hyphenated slugs and update the root README whenever a pet is added or its display information changes.

## Pet creation and updates

1. Read the backed-up [create-pet skill](skills/create-pet/SKILL.md), its linked references, and the target pet's existing request and QA files before changing artwork.
2. Preserve existing pets unless the user explicitly asks to replace or update one. For a new pet, add a new slug folder.
3. Match the requested art direction. For game characters, first look for original sprites and prefer preserving the pixel-art source when the user asks for it; keep source attribution with the files. For new or missing animation art, use ImageGen with the source sprite sheet attached as the identity reference. Avoid glossy toy or Disney-like styling when the user asks for darker art.
4. Use the bundled scripts under `skills/create-pet/scripts/` for extraction, composition, chroma cleanup, atlas validation, direction continuity, and quality validation. New pets use v2: transparent PNG/WebP, exactly 1536x2288 pixels, 8 columns by 11 rows, 192x208 cells, 73 populated frames.
5. Inspect the standard animation contact sheet, labeled look-direction sheet, and all loop transitions. A wrong or ambiguous cardinal, clipped art, broken prop, accidental hole, or failed bundled gate blocks upload.
6. Render previews from the final encoded sheet and show motion to the user before upload. Preserve the preview and every required QA report in that pet's folder.
7. Run the Pets sprite-sheet preflight against the exact final file. Continue only when `valid` is true. Prepare one upload session, create the pet with the requested name and description, select it only when requested or clearly part of the user's request, then list pets and verify its stable ID and active state.
8. Do not commit temporary upload-session IDs, authenticated URLs, or credentials.

## README portraits

Use one transparent PNG per pet in `images/`, placed side by side in the README. Derive each portrait from that pet's first idle frame, preserving the transparent alpha channel. Verify transparency and visual scale before updating the README.

## Publishing each pet in the README

When adding a pet, update the root `README.md` in the same change:

1. Add one heading cell and one portrait cell to the side-by-side image table. Use `images/<slug>.png`, a descriptive `alt`, and a consistent display width.
2. Add a row to the Pets table with the display name, short appearance description, and stable ChatGPT Pet ID returned by the create flow.
3. Add source artwork and its attribution/link under `pets/<slug>/source/`; do not embed temporary upload URLs or claim third-party art is original.
4. Check that every README image path exists, the pet IDs and names match `list_pets`, and all table rows line up. Preview the rendered README, then commit and push the README and pet files together to `origin/main`.

## Changes and verification

- Make focused changes; preserve useful intermediate source and QA artifacts.
- Run the relevant bundled validation scripts for sprite changes. For documentation-only changes, check Markdown links, image paths, pet names, and repository instructions.
- Before pushing, inspect `git status`, review the staged diff, commit with a concise message, and push to `origin main`.
- Verify the remote branch and repository visibility after publication changes.
