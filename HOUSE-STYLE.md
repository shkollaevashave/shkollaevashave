# House style and running the site

This file is for whoever maintains the site, person or Claude. Give it to Claude at the start of any session that touches the site. Everything needed to carry on is here.

## The setup

- The site is built with Jekyll and hosted on GitHub Pages from the institute's GitHub organisation.
- The repository is named `[org-name].github.io`. That name puts the site at the root of the address, so `baseurl` stays empty and links work without changes.
- The repository is public. Nothing goes in it that isn't meant for visitors: no phone numbers of staff, no consent forms, no drafts with private details.
- The site is in Albanian. English follows later (see below).

## Where things live

| What | Where |
| --- | --- |
| Opening hours, address, email, phone | `_data/info.yml` (change once, updates every page) |
| Menu items and interface words | `_data/ui.yml` |
| News posts | `_posts/YYYY-MM-DD-slug.md` |
| Fixed pages | `historia/`, `vizitoni/`, `udhetime-shkollore/`, `kontakt/` |
| Images | `assets/img/` |
| Colours and fonts | top of `assets/css/style.css` |
| Staff submission template | `docs/shablloni-per-stafin.md` |

## Publishing a news post

1. Staff send a completed submission (template in `docs/`). Check the consent line is answered before doing anything else. No answer means no photos of pupils.
2. Create a branch named after the post, e.g. `lajm-dita-e-mesuesit`.
3. Add the post as `_posts/2026-03-07-dita-e-mesuesit.md`. The date in the filename is the publication date.
4. Add images to `assets/img/`, named with the same date prefix.
5. Open a pull request. The maintainer reads it and merges. The live site updates within a few minutes.

Post front matter:

```yaml
---
title: "Titulli i lajmit"
image: /assets/img/2026-03-07-dita-e-mesuesit.jpg
image_alt: "Përshkrim i fotos për lexuesit me ekran"
image_credit: "Emri i fotografit"
---
```

`image`, `image_alt` and `image_credit` are optional, but if `image` is set, `image_alt` is required.

## Writing

- Standard Albanian with correct ë and ç. Never substitute e or c.
- The first paragraph appears in the news list on its own, so it must say what happened, when and where.
- Short paragraphs. Plain words. Write for a teacher planning a trip or a family on a Saturday.
- Dates in text: `7 mars 2026` (day, lower-case month, year). The site formats post dates this way automatically.
- Times in 24-hour form: `09:00–16:00`.
- Keep staff wording where possible. Fix spelling and structure; don't rewrite their voice.
- Historical names, dates and place names must come from the staff submission or a cited source. Never fill a gap from general knowledge. Flag it and ask.

## Images

- Resize to 1600 px on the long edge, save as JPEG at about 80% quality. Aim for under 300 KB.
- Lower-case file names, hyphens, no spaces or ë/ç: `2026-03-07-klasa-historike.jpg`.
- Every image needs alt text in Albanian describing what is in it.
- Credit the photographer when known.
- Pupils: only if the submission confirms consent. Otherwise crop them out or leave the photo out.
- Archive photos: note the source (archive name or donor).

## Changing opening hours

Edit `_data/info.yml` only. The home page, Visit page, Contact page and the Google listing data all read from it. Then update the Google Business Profile to match, by hand.

## Adding English later

1. Add an `en:` block to `_data/ui.yml` mirroring `sq:`, with English nav URLs under `/en/`.
2. Create `en/index.html`, `en/history/`, `en/visit/`, `en/school-trips/`, `en/news/`, `en/contact/`, each with `lang: en` in front matter.
3. Give English posts `lang: en` and a `permalink` under `/en/news/`. Filter news lists by `lang`.
4. Add `label_en` to each hours row in `_data/info.yml`.
5. Add a language switch link in `_includes/header.html`.

A native speaker checks every translation of historical content before it is merged.

## Switching to the .org.al domain

1. In the repository: Settings → Pages → Custom domain → enter the domain.
2. At the registrar: four A records for the bare domain pointing to GitHub's Pages IPs (check GitHub's docs for the current list), and a CNAME for `www` pointing to `[org-name].github.io`.
3. Wait for the certificate, then tick Enforce HTTPS.
4. Change `url` in `_config.yml` to the new domain.
5. Verify the domain in the organisation's settings.
6. Check that the old github.io address redirects.

## Previewing on a laptop

```
bundle install
bundle exec jekyll serve
```

Then open http://localhost:4000.
