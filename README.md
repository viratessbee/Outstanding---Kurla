# Outstanding Bills – Salesperson View

Static website (GitHub Pages). Each salesperson picks their name and sees party-wise,
bill-wise outstanding with **days counted from the dispatch date**.

## One-time setup
1. Create a new GitHub repo (e.g. `outstanding`).
2. Upload `index.html`, `data.json`, `convert.py` (drag & drop on the repo page → Commit).
3. Repo → **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main` / `(root)` → Save.
4. Link will be `https://<your-username>.github.io/<repo-name>/`
   Per-salesperson link: add `#Name`, e.g. `.../outstanding/#Nitish`

## Daily update
```
pip install openpyxl
python convert.py OS_<date>.xlsx      # creates a fresh data.json
```
Upload the new `data.json` to the repo (Add file → Upload files → replace). Done.

## Marking bills
Each bill has **Cleared** / **Cheque** buttons and an **Undo**. Marks are stored in the salesperson's
own browser (localStorage), keyed by salesperson + book + invoice no + invoice date, so they stay after
refresh and after a new `data.json` is uploaded. Use *Backup marks* / *Restore* to move marks to another phone.
