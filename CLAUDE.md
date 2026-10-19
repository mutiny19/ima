# Working on this repo

Read this first if you are an AI session or a new contributor. It is the short version of how the
site is built and the rules that are not negotiable.

## What it is

A static GitHub Pages site (no build step, no framework) for off-grid communications in Indiana.
It is a pivot point, not an authority: it links to each protocol's official docs and to each
group's own pages, and it only publishes Indiana-specific suggestions as proposals.

## Rules

1. **No personal information, anywhere.** No personal names, GitHub user names, e-mail addresses,
   individual callsigns, home locations, or personal node positions in pages, data, commit
   messages, commit authors, workflows, or issue templates. Commits are authored
   `Indiana Mesh <mutiny19@users.noreply.github.com>`. Run `python3 tools/check_pii.py` before
   every push; keep your own strings in an untracked `.pii-local` and pass `--names .pii-local`.
2. **Nothing unkind about any other network or group.** Describe each in its own words, link to
   its own site, never compare or rank.
3. **Link, don't copy.** If an official source explains it, link there.
4. **Proposals stay proposals.** Region-tag structures on `advanced/` are "for consideration";
   the page says so and must keep saying so until the community decides.
5. **Nothing simulated ships.** Real data from the named sources or nothing.

## Layout

| Path | What |
|---|---|
| `index.html` + `assets/home.js` | Home: map band (repeaters, NWS alerts, nets, Kp), dashboard, settings accordion, report form |
| `meshcore/index.html` | Start page: first radio to first message, nearby groups table |
| `advanced/index.html` | Region settings: three proposed structures (Simplest, Abbreviated, County & district) |
| `advanced/regions.js` | **Every table the region page draws from**: metro codes, regions, districts, neighbours, bands |
| `advanced/counties.js` | County outlines for the maps (generated from Census data) |
| `advanced/builder.js` | County & district builder logic |
| `advanced/modes.js` | Simplest and Abbreviated modes, mode switch |
| `emergency/index.html` | Agencies article (APA citations) |
| `live/index.html` | Where to watch live traffic |
| `assets/site.css`, `theme.js`, `site.js` | Shared styles, pre-paint theme, nav/theme/copy behaviour |
| `data/` | Nightly repeater inventory, yearly county reference, nets, settings JSON |
| `tools/` | The scripts the workflows run, plus `check_pii.py` and `check_links.py` |
| `.github/workflows/` | nightly `nodes.yml`, yearly `reference.yml`, weekly `links.yml` |

Each page keeps its own CSS inline in a `<style>` block; shared rules live in `assets/site.css`.
Scripts are classic (non-module) and share globals in load order, so `regions.js` must load
before `builder.js` and `modes.js`.

## Changing things

- Site name, Discord invite, repo URL: they appear in the header and footer of every page.
  `grep -rl "discord.gg" --include=*.html .` finds them all; `FORKING.md` has the checklist.
- Region tags, metros, groups' tags: edit `advanced/regions.js` only.
- Nearby groups: the table on `meshcore/index.html`, the state cells below it, and step 4 of the
  Abbreviated mode on `advanced/index.html`.
- Nets: `data/nets.json`. Suggested settings: `data/settings/*.json`.

## Testing

```
python3 -m http.server 8000
```
Open each page, switch the theme, use the phone width. For a scripted check, load each page in
a headless browser and assert no page errors and no 404s for local assets; `advanced/` should
produce `region def us|* us-in|* ind` after clicking `ind` in Simplest mode.

## Publishing

GitHub Pages serves `main` from the repo root. Push only from a clone whose history is clean of
personal information. Never force-push over the nightly workflow's commits; `git pull --rebase`
first.
