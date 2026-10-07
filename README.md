# ION Solar Welcome Call Guide

A step-by-step web app that walks reps through ION Solar welcome calls, based on the Welcome Call Scripts SOP (effective 7 October 2026).

The rep picks what the customer bought, how they're paying, and the state. The app then loads the matching script with each state's rules applied:

- English
- Las Vegas
- LR
- Las Vegas LR
- Battery Only LR
- Battery Only Purchase
- AHA

Reps then work through the call one line at a time.

## Files

- `index.html` is the entire app. It is a single self-contained file with no build step and no dependencies to install.

## Publish with GitHub Pages

1. Create a new repository and upload `index.html` and `README.md` to the root of the `main` branch.
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, set the source to **Deploy from a branch**, then choose `main` and `/ (root)`, and save.
4. After a minute or two, the site is live at `https://<your-username>.github.io/<repo-name>/`.

You can also open `index.html` directly in a browser without hosting it anywhere.

## Updating the scripts

All script wording is in the `T` object near the top of the `<script>` section in `index.html`. Edit the text there, commit, and GitHub Pages redeploys automatically.

The `sections()` function controls which lines appear for each script, state, and payment type. State-specific rules are defined there:

- the HOA states (IL, CO, OR, NM, UT)
- South Carolina's 10-day cancellation
- the UT/OH/MD/MA cash split
- the Colorado backup-power line
- the Arizona thermostat check
- the Nevada notices

## Notes

- Call progress is saved in each rep's own browser (localStorage), so a page refresh doesn't lose a call in progress. Nothing is sent to a server.
- Fonts load from Google Fonts. If they're blocked, the app falls back to system fonts.
