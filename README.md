# Kishan Prajapati — Portfolio

A one-page, bento-grid portfolio. **One file (`index.html`)**, no framework, no build step, no dependencies to install. Open it in a browser and it works.

---

## 1. What's in this folder

| File | What it is |
|---|---|
| `index.html` | The whole site — HTML, CSS, JavaScript, and your photo (embedded) |
| `README.md` | This guide |
| `CHANGELOG.md` | Log of every change — add a line each time you update |
| `PROMPT.md` | The original design brief (why things look the way they do) |

---

## 2. Go live for free (pick ONE)

### Option A — GitHub Pages (recommended)
Free forever, URL looks like `https://yourname.github.io`, and it's a GitHub profile recruiters can click too.

1. Sign up at https://github.com (free). Pick a professional username, e.g. `kishan-prajapati`.
2. Click **+ → New repository**.
   - Name it **exactly** `<your-username>.github.io` (e.g. `kishan-prajapati.github.io`)
   - Set it **Public** → **Create repository**.
3. Click **uploading an existing file** → drag in `index.html` (and the `.md` files if you want) → **Commit changes**.
4. Go to **Settings → Pages**. Under *Build and deployment*: Source = **Deploy from a branch**, Branch = **main**, folder **/(root)** → **Save**.
5. Wait 1–2 minutes. Your site is live at `https://<your-username>.github.io`.

**To update later:** open the repo → click `index.html` → pencil icon ✏️ → edit → **Commit changes**. Live in ~1 minute.

### Option B — Netlify Drop (fastest, 60 seconds)
1. Go to https://app.netlify.com/drop
2. Drag this whole folder onto the page.
3. You get a live URL instantly (e.g. `random-name.netlify.app`). Sign up free to keep it and rename it to `kishan-prajapati.netlify.app` under **Site settings → Change site name**.

**To update:** Netlify → your site → **Deploys** → drag the folder in again.

### Option C — Cloudflare Pages
https://pages.cloudflare.com → Create project → **Direct upload** → upload the folder. URL: `yourname.pages.dev`.

### About "free domains"
Avoid free `.tk / .ml / .ga`-style domains — they're unreliable and often flagged as spam. `github.io`, `netlify.app` and `pages.dev` are free **and** look normal to recruiters.

**Optional paid domain** (e.g. `kishanprajapati.dev`, roughly ₹800–1,500/year): buy from Cloudflare, Namecheap or GoDaddy, then:
- GitHub Pages: **Settings → Pages → Custom domain** → enter it, and follow the DNS instructions shown.
- Netlify: **Domain management → Add a domain**.
HTTPS is free and automatic on all three.

---

## 3. Put it on LinkedIn (after it's live)

1. **Profile → Edit intro → Website** → paste your URL → link text: `Portfolio`.
2. **Featured → + → Add a link** → paste your URL.
3. **About section** → add `Case studies: <your URL>` above the email line.
4. Post about it — lead with one case study (the warranty-number race condition is the strongest), link at the end.

---

## 4. How to change content

**All content lives in one place:** open `index.html`, search for `const PORTFOLIO = {`. Edit text inside the quotes. You never need to touch the HTML or CSS for content changes.

**Rule:** make a field empty (`""` or `[]`) and that element disappears from the page.

| To change… | Edit this key | Example |
|---|---|---|
| Big title at top | `masthead`, `mastheadSub` | `masthead: "Full stack, end to end"` |
| Availability chip | `status` | `status: "Open to full-stack roles · available now"` |
| Photo | `photoUrl` | see §5 |
| Email / phone / links | `email`, `phone`, `linkedin`, `github` | `github: "https://github.com/kishan-prajapati"` |
| Résumé button | `resumeUrl` | Google Drive link set to *Anyone with the link* |
| Roima numbers (phone tile) | `latest.rows` | `["180+", "tickets closed"]` |
| "Typical week" notifications | `toasts` | `["Title", "Text", "Mon"]` |
| Career chart | `years` | months worked per year: `g` = Gateway, `r` = Roima |
| Job history (chart pop-ups) | `roles` | `points: ["...", "..."]` |
| Case studies | `cases` | see below |
| Countries | `countries` | `["Norway", "r"]` |
| Skills | `skills` | `["Backend", ["C#", "..."]]` |
| Award / certificate | `award` | |

### Add a new case study
Copy an existing block inside `cases: [ ... ]`, paste it after the last one (keep the comma between blocks), then change:
```js
{ id: "short-unique-id",        // used in the link: yoursite/#short-unique-id
  from: "Roima",                // green tag
  thumb: "lock",                // icon: lock | sync | tree | chart
  title: "...", blurb: "...", meta: "...",
  problem: "...",
  did: ["...", "..."],
  result: "...",
  tags: ["C#", "SQL Server"] }
```

### Add a public GitHub project
Set `github:` to your profile URL. A GitHub button appears in the contact tile.

### Add a new country or employer
Countries use the employer key (`g` or `r`). For a new employer, add it to `employers` (e.g. `n: "New Co"`), use `n` in `years` and `countries`, and add its colour in the chart CSS (`.seg.n{background:...}`).

---

## 5. Changing the photo

The photo is embedded in `index.html` as text (a `data:image/jpeg;base64,...` string), so the site stays one file.

**Easy way:** upload `photo.jpg` (square, ~400×400px, under 100 KB) next to `index.html`, then set:
```js
photoUrl: "photo.jpg",
```
Leave `photoUrl: ""` to show your initials instead.

---

## 6. Features (for reference)

- Bento grid: 4 columns on desktop → 2 on tablet → 1 on phone
- Case studies open in a pop-up; each has its own link (`yoursite/#warranty-registration`) — share a specific one with a recruiter
- Chart bars open that year's roles (`yoursite/#year-2024`)
- Browser **Back** and **Esc** close pop-ups
- Light / dark theme toggle (remembered per visitor)
- Copy-email button
- Animations: one entrance sequence, count-up numbers, bars grow when visible, notifications arrive in order
- Respects "reduce motion" accessibility setting (all animation off)
- Content stays visible even if JavaScript fails
- No trackers, no cookies, no external scripts — only Google Fonts

---

## 7. Before every update — checklist

1. Numbers match your résumé and LinkedIn (tickets, dates, countries).
2. No client names, ticket IDs, table names or internal page IDs added.
3. Open `index.html` locally → click each case study → check phone view (browser dev tools, ~390px width).
4. Add a line to `CHANGELOG.md`.
5. Upload / commit.

**If the page shows blank or broken after an edit:** you almost certainly broke a quote or comma in `PORTFOLIO`. Press **F12 → Console**; the error shows the line number. Common causes: a missing comma between items, or an unescaped `"` inside text (use `'` instead, or `\"`).

---

## 8. Optional upgrades (not done yet)

- **LinkedIn preview image** — make a 1200×627 `og.png`, upload it, then uncomment the `og:url` / `og:image` lines near the top of `index.html`.
- **Visitor analytics** — free at https://www.goatcounter.com: sign up, paste their one-line script before `</body>`.
- **A public repo** — a small ASP.NET Core + Angular demo of the warranty-claim flow, linked via `github`. This is the single biggest improvement still open.
