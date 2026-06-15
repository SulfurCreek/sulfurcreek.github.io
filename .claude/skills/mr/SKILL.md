---
name: mr
description: Use when the user types /mr or asks to commit and push the current changes to the live site.
---

# mr — commit + push

Stage everything, commit, and push to `main` (which deploys to GitHub Pages).

## Steps

1. Show what will be committed:
   ```bash
   git status -s
   ```
2. Stage all changes:
   ```bash
   git add -A
   ```
3. Commit. If the user gave a message after `/mr`, use it. Otherwise write a short
   message (in English) summarizing the change from the diff. Always end with the
   Co-Authored-By trailer:
   ```bash
   git commit -m "<summary>

   Co-Authored-By: Claude Opus 4.8 (1M context) <noreply@anthropic.com>"
   ```
4. Push:
   ```bash
   git push origin main
   ```
5. Report the resulting commit range (e.g. `0bca883..2075dec`) and remind the user
   GitHub Pages redeploys in ~1-2 min.

## Notes

- This repo deploys straight from `main` — pushing publishes the live site. That is intended; do not create a branch.
- If there is nothing to commit (`git status -s` is empty), say so and stop.
