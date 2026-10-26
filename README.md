# Outstanding Bills – Salesperson View

Static website (GitHub Pages). Each salesperson picks their name and sees party-wise,
bill-wise outstanding with **days counted from the dispatch date**.

## One-time setup
1. Create a new GitHub repo (e.g. `outstanding`).
2. Upload `index.html`, `data.json`, `convert.py` (drag & drop on the repo page → Commit).
3. Repo → **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main` / `(root)` → Save.
4. Link will be `https://<your-username>.github.io/<repo-name>/`
   Per-salesperson link: add `#Name`, e.g. `.../outstanding/#Nitish`

## Daily update (no Python needed)
1. Open `update.html` (double-click it on your computer, or use `.../outstanding/update.html` online).
2. Choose today's Excel report -> it shows "Read OK".
3. Click **Download data.json**.
4. GitHub repo -> Add file -> Upload files -> drag `data.json` -> Commit changes.
(`convert.py` still works as an alternative: `python convert.py OS_<date>.xlsx`)

## Marking bills
Each bill has a tick box; ticked bills turn green (cleared); untick to undo. Marks are stored in the salesperson's
own browser (localStorage), keyed by salesperson + book + invoice no + invoice date, so they stay after
refresh and after a new `data.json` is uploaded. Use *Backup marks* / *Restore* to move marks to another phone.
