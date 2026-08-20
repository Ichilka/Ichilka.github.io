# Danny Luong-Chau — Portfolio

Dark-glass portfolio for an IT Director. Built on Jekyll, hosted free on
GitHub Pages, edited from the browser at `/nin` (Sveltia CMS). You never
touch HTML to update content.

## Deploy (one time, ~10 minutes)

1. **Create the repo.** Push these files to a new GitHub repository.
   - Name it `USERNAME.github.io` → site lives at `https://USERNAME.github.io`
   - Any other name → site lives at `https://USERNAME.github.io/REPONAME`
2. **Enable Pages.** Repo → Settings → Pages → Source: *Deploy from a branch*
   → Branch: `main`, folder `/ (root)`. GitHub builds Jekyll automatically.
3. **Set the base URL** in `_config.yml`:
   - `USERNAME.github.io` repo → leave `baseurl: ""`
   - Any other repo name → set `baseurl: "/REPONAME"`
   - Set `url:` to your full site URL either way.
4. **Wire up the CMS.** In `nin/config.yml`, change
   `repo: YOUR-USERNAME/YOUR-REPO` to your actual repo.
5. **Custom domain (optional).** Settings → Pages → Custom domain
   (e.g. `portfolio.ichikaonline.com`), then point a CNAME record at
   `USERNAME.github.io` in your DNS.

## Editing content — the `/nin` admin

Go to `https://your-site/nin/`, choose **Sign in with GitHub Token**, and
paste a fine-grained personal access token:

GitHub → Settings → Developer settings → Fine-grained tokens → Generate:
- Repository access: **only this repo**
- Permissions: **Contents → Read and write**

The login screen links you to the token page with scopes pre-selected.
Every "Publish" in the CMS is a Git commit — GitHub Pages redeploys
automatically in ~1 minute.

What you can edit there:
| Section | What it controls |
|---|---|
| Projects & Case Studies | Add/edit case studies and homelab projects |
| Profile | Name, tagline, hero stats, contact links |
| Career Timeline | Add a promotion or new job |
| Expertise Grid | Skill domains and items |
| Certifications | Add a cert |

Prefer editing files directly? Same content lives in `_data/*.yml` and
`_projects/*.md`. Edit, commit, push — same result.

## Adding things (cheat sheet)

- **New case study:** CMS → Projects → New, category *Case Study*.
  Or copy any file in `_projects/` and edit it.
- **New job / promotion:** CMS → Career Timeline → add a position at the
  top, tick *Current Role*, untick it on the old one.
- **New cert:** CMS → Certifications → add row. Done.
- **Images:** upload via CMS; they land in `assets/images/uploads/`.

## Before going live — checklist

- [ ] Verify career **dates** in `_data/experience.yml` (best guesses used)
- [ ] Real **LinkedIn / GitHub / email** in `_data/profile.yml`
- [ ] `repo:` set in `nin/config.yml`
- [ ] `url:`/`baseurl:` set in `_config.yml`

## Local preview (optional)

```bash
gem install bundler && bundle install
bundle exec jekyll serve
# → http://localhost:4000
```

Not required — GitHub builds the site for you on every push.

## Structure

```
_config.yml          Jekyll/site settings
_data/               ← all your content (profile, jobs, skills, certs)
_projects/           ← one .md file per project/case study
_layouts/            page templates (rarely touched)
assets/              css / js / images
nin/                 browser CMS (Sveltia)
```
