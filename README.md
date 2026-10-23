# 1TTD Trainer — Public Solution Library

This repository holds **only public, approved** Blood Bowl One-Turn Touchdown (1TTD) recordings for [1ttd.co.uk](https://1ttd.co.uk/). Site features, rules logic, private submissions and the owner review dashboard do **not** belong here.

## First publication

1. Create a **Public** GitHub repository named `1ttd-library` (the name matters for the example URLs).
2. Extract this ZIP on your computer. Do **not** upload the ZIP as a single file.
3. On the repository page choose **Add file → Upload files** and drag all extracted files and the `data` folder into the upload area (GitHub supports folder drag-and-drop). Commit them to the `main` branch.
4. Select **Settings → Pages → Build and deployment → Source: Deploy from a branch → main → /(root) → Save**.
5. Open the GitHub Pages URL from Settings → Pages. It normally resembles `https://YOUR-USERNAME.github.io/1ttd-library/`.
6. Check that `https://YOUR-USERNAME.github.io/1ttd-library/data/catalog.json` displays the catalogue.
7. Only after that, connect the production site once to fetch the GitHub Pages catalogue and its recording files. **This starter ZIP alone does not alter or connect 1ttd.co.uk.**

Github Pages publishing may take several minutes. Do not change your `1ttd.co.uk` DNS or Netlify domain settings to use this library.

## How future updates work (after 1ttd.co.uk is connected)

- Create the full recording in Free Play / private development app; export a `sequence` JSON.
- Review it privately; verify rules as appropriate and obtain permission for any attributed content.
- Add the **approved** recording to `data/sequences/NAME.json`.
- Add an entry to `data/catalog.json` under `challenges`, following the existing `sporran-four-push` entry. Unique `id` and `file` must match the path exactly (`data/sequences/NAME.json`). `published` must be `true` to show publicly.
- Commit both files to GitHub. GitHub Pages will publish the new static content. This does **not** redeploy Netlify.

In the future the local owner dashboard can generate the updated catalogue and upload it to GitHub via a reviewed action, but **no public website must contain a GitHub token**.

## Standard metadata in the existing catalogue

| Field | Use |
|---|---|
| `id` | Stable slug such as `ma6-generic-4-push` |
| `ma` | Scorer Movement Allowance: 6, 7, 8, or 9 |
| `name` | Short descriptive title |
| `attackingTeam` | Race name, or `Generic` |
| `defendingTeam` | Race name or `null` for generic opposition |
| `creatorDisplay` | Name credited publicly |
| `rulesetId` | `BB2025` when verified for that ruleset, or explicitly labelled demonstration |
| `defenceFormation` | e.g. `Anti-Blitz`, `Narrow LOS`, `Push denial` |
| `pushes` | Count of intended pushes |
| `skillsRequired` | List of skills needed for this route |
| `coachNotes` | Explanation, assumptions and caveats |
| `file` | Path to full JSON replay |
| `published` | `true` only after review |

Source credits / links to the original YouTube or FUMBBL inspiration can be added as new optional metadata during the one-time website integration. Do not confuse original idea credit with the person who recorded the demo.

## Safety / licensing

This is a **PUBLIC** repository. Never upload `PRIVATE_ADMIN/`, queued submissions, reviewer notes, private coach contact information, access tokens, passwords or backups. Don't upload images or recordings belonging to others without appropriate permission; linking to the source and crediting it is generally preferable.

Independent fan project by Sporran. Not endorsed by Games Workshop.
