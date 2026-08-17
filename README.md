# EPF | European Professional Football

Compact league dashboard site — blue/black theme, animated loading screen with the EPF crest, and a single-panel dashboard covering Fixtures, Results, List of Teams, Most Goal Scorers, Most Assists, Most Clean Sheets and the League Table (tab-based, so nothing is a long separate page — click a card, the panel below updates instantly).

## 📁 Structure (everything in the root, no subfolders)

```
.
├── index.html
├── logo.png       ← EPF crest, used on the loading screen, header and hero
├── favicon.png
├── .nojekyll
├── .gitignore
└── README.md
```

## 🚀 Deploy on GitHub Pages

1. Create a repository → upload `index.html`, `logo.png`, `favicon.png`, `.nojekyll` (Add file → Upload files, straight into the root)
2. **Settings → Pages → Source:** branch `main`, folder `/ (root)` → Save
3. After about a minute your site is live at `https://YOUR-USERNAME.github.io/YOUR-REPO/`

## ✏️ Editing content

Everything lives in arrays near the bottom of `index.html`, inside `<script>`. Terminology is consistent everywhere: clubs are called **Team**, athletes are called **Player**.

**Fixtures** — array `FIXTURES`:
```js
{ home:"Team Alpha", away:"Team Nova", date:"Aug 22", time:"20:00" },
```

**Results** — array `RESULTS`:
```js
{ home:"Team Alpha", homeScore:2, away:"Team Nova", awayScore:1, date:"Aug 15" },
```

**List of Teams** — array `TEAMS`:
```js
{ name:"Team Alpha", founded:"2024", players:18 },
```

**Most Goal Scorers / Most Assists / Most Clean Sheets** — arrays `TOP_SCORERS`, `TOP_ASSISTS`, `CLEAN_SHEETS` (currently empty, they show a friendly placeholder until the season starts):
```js
{ rank:1, player:"Player Name", team:"Team Alpha", goals:9 },
```

**League Table** — array `LEAGUE_TABLE`:
```js
{ pos:1, team:"Team Alpha", played:5, won:4, drawn:1, lost:0, gf:14, ga:6, pts:13 },
```

## 🎮 Discord

The "Join Discord" button (header + hero) links to `https://discord.gg/Dn62CeCSx` — update it in `index.html` if it ever changes (search for `discord.gg`).

## 🖼️ Logo & background icons

`logo.png` is your real EPF crest — swap the file (same name) to update it everywhere at once. The faint floating icons in the background (ball, shield, trophy, whistle) are abstract SVGs generated in code — no external images needed; edit them in the `FLOATING FOOTBALL ICONS` block at the end of `index.html`.

## ✨ Loading screen animation

Logo pulses gently while the bar fills, then on completion the whole logo+label group drops down and fades while the bar fades separately, before the site reveals with a staggered fade-up.
