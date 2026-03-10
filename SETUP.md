# Setup Guide — labishbardiya GitHub Profile README

Complete checklist to get everything running. Do these in order.

---

## Step 1 — Create the Profile Repo

1. Go to github.com/new
2. Repository name: `labishbardiya` (must match your username exactly)
3. Check "Public"
4. Check "Add a README file"
5. Create repository

---

## Step 2 — Upload the Files

Copy files from this package into your repo:

```
labishbardiya/
├── README.md                         ← main profile file
├── assets/
│   └── banner.png                    ← your LinkedIn banner image
└── .github/
    └── workflows/
        ├── waka-readme.yml
        ├── activity.yml
        ├── snake.yml
        └── dynamic-profile.yml
```

Note: The `workflows/` folder in this package maps to `.github/workflows/` in your repo.

---

## Step 3 — Fill in the Placeholders

Open README.md and replace these before pushing:

| Placeholder | Replace with |
|-------------|-------------|
| `./assets/banner.png` | Your LinkedIn banner (1584×396px exported as PNG, saved in `assets/`) |
| `DISCORD_LINK_PLACEHOLDER` | Your Discord invite link (e.g. `discord.gg/abc123`) or profile link |
| `RESUME_PDF_URL_PLACEHOLDER` | Raw GitHub URL to your resume PDF (upload it to this repo under `assets/resume.pdf` then use the raw URL) |
| `bruxlix` (pinned repo card) | Actual repo slug once it's public |
| `curenet` (pinned repo card) | Actual repo slug once it's public |

---

## Step 4 — Add GitHub Secrets

Go to: Your repo → Settings → Secrets and variables → Actions → New repository secret

| Secret Name | Where to get it |
|-------------|----------------|
| `WAKATIME_API_KEY` | wakatime.com → Settings → API Key |
| `GH_TOKEN` | github.com → Settings → Developer Settings → Personal Access Tokens (Classic) → select `repo` scope |

---

## Step 5 — Create the `output` Branch (for snake)

Run this once in your terminal (or use GitHub's UI to create an empty branch):

```bash
git clone https://github.com/labishbardiya/labishbardiya.git
cd labishbardiya

git checkout --orphan output
git rm -rf .
git commit --allow-empty -m "Init output branch"
git push origin output

git checkout main
```

---

## Step 6 — Trigger Workflows Manually (first run)

Go to: Your repo → Actions tab → select each workflow → "Run workflow"

Run in this order:
1. `Generate Snake Animation` — creates SVGs in output branch
2. `Waka Readme Stats` — populates WakaTime section
3. `Update README with GitHub Activity` — populates activity section
4. `Dynamic Profile Page` — populates recent commits section

After the first manual run, all workflows run automatically on their schedule.

---

## Step 7 — LinkedIn Banner

1. Go to your LinkedIn profile
2. Edit your banner (recommended: design in Figma at 1584×396px, purple/blue gradient matching README theme)
3. Download the PNG
4. Upload to `assets/banner.png` in this repo
5. The README already references `./assets/banner.png`

---

## What Each Tool Handles

| Section | Tool | Update Frequency |
|---------|------|-----------------|
| Typing taglines | DenverCoder1/readme-typing-svg | Static (changes when you edit) |
| Tech logos + progress bars | harish-sethuraman/readme-components | Static |
| WakaTime coding stats | anmol098/waka-readme-stats | Daily |
| GitHub stats cards | anuraghazra/github-readme-stats | Real-time |
| GitHub streak | DenverCoder1/github-readme-streak-stats | Real-time |
| GitHub trophy | ryo-ma/github-profile-trophy | Real-time |
| Recent activity | jamesgeorge007/github-activity-readme | Every 30 min |
| Dynamic commits | umutphp/github-action-dynamic-profile-page | Daily |
| Contribution snake | Platane/snk | Daily |
| Holopin badges | holopin.me | Real-time |
| Profile views | komarev.com/ghpvc | Real-time |

---

## Color Reference (for Figma banner or other customization)

| Use | Hex |
|-----|-----|
| Primary purple | `#7C3AED` |
| Accent blue | `#3B82F6` |
| Background dark | `#0D1117` |
| Text light | `#C9D1D9` |
| Stats theme | `tokyonight` |

---

## Quick Verification Checklist

- [ ] Profile repo name matches GitHub username exactly
- [ ] README.md has no broken image links
- [ ] `DISCORD_LINK_PLACEHOLDER` replaced
- [ ] `RESUME_PDF_URL_PLACEHOLDER` replaced
- [ ] LinkedIn banner uploaded to `assets/banner.png`
- [ ] Both secrets added (WAKATIME_API_KEY, GH_TOKEN)
- [ ] `output` branch created
- [ ] All 4 workflows run at least once manually
- [ ] Bruxlix and CureNet repo slugs updated in pinned cards when repos go public
