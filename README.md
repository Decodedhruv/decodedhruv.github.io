# Dhruva’s website — Version 0.1

A personal notebook built directly from [Academic Pages](https://github.com/academicpages/academicpages.github.io), using Jekyll, Liquid, Sass and Markdown. The original layouts, includes, Sass modules and MIT licence remain available; the active design is in `_layouts/notebook*`, `_includes/notebook*` and `_sass/_notebook.scss`.

**Website:** https://decodedhruv.github.io

**Custom domain:** not connected. Do not add a CNAME or change DNS until approved.

## Everyday editing

On GitHub, open a file and use the pencil button to edit it. Save with **Commit changes**. The **Actions → pages build and deployment** run builds and publishes the site, usually within a few minutes. The instructions below use repository-relative paths.

### 1. Add a Note

Choose **Add file → Create new file**. Name it `_posts/2026-10-01-a-title-for-the-note.md`. Replace the date and title in this example:

```markdown
---
title: A title for the note
date: 2026-10-01 10:00:00 +0100
categories: [notebook]
tags: [London, transport]
description: "A short description for the archive."
selected: false
---
Write your note here. Ordinary Markdown works.

## A heading

A paragraph with *italics*, **bold**, and [a link](https://example.com).
```

The filename must start with `YYYY-MM-DD-`. Newest notes appear first. Use `+0100` during British Summer Time and `+0000` in winter. Future-dated notes stay hidden until a build runs after that date (there is no scheduled publishing in v0.1). Use `published: false` in the front matter to hide a draft, then remove that line when ready. Draft source in a public repository is still public; do not put private material there.

The sample is `_posts/2026-09-30-a-place-for-notes.md`; edit or delete it whenever you like. Tags/categories are displayed as labels in v0.1, not separate filter pages.

### 2. Add a Work/project

Create `_work/project-name.md`:

```markdown
---
title: Project name
order: 2
status: Work in progress
description: "A one-sentence description."
tags: [research, development]
selected: true
---
Describe the project here.
```

`order` controls the Work listing. `selected: true` also puts it on the homepage. The address will be `/work/project-name/`.

### 3. Add an external Writing link

Create `_writing/essay-name.md`:

```markdown
---
title: Essay title
date: 2026-09-30
publication: Publication name
external_url: https://example.com/the-essay
description: "A brief description of the piece."
selected: true
---
```

The Writing listing links directly to the original publication. No need to copy the essay here. Use `selected: false` to leave it off the homepage. To publish an essay locally, omit `external_url` and write below the second `---`.

### 4. Add a photograph

Open `images/notes` on GitHub, choose **Add file → Upload files**, and upload a sensibly sized image (around 1600 pixels wide, ideally below 400 KB). Use a simple filename such as `london-evening.jpg`.

Inside a Note, use:

```markdown
![A descriptive sentence about what the photograph shows.](/images/notes/london-evening.jpg)

*London, September 2026.*
```

For a semantic caption and lazy loading:

```html
<figure>
  <img src="/images/notes/london-evening.jpg"
       alt="A descriptive sentence about what is visible."
       width="1600" height="1067" loading="lazy" decoding="async">
  <figcaption>London, September 2026. Photograph by Dhruva Nagesh.</figcaption>
</figure>
```

Use the image’s actual dimensions and your own caption/credit. No photographs are included in v0.1 because none have been supplied.

### 5. Add a navigation item

Edit `_data/navigation.yml` and add:

```yaml
  - title: Books
    url: /books/
```

Then create `_pages/books.md`:

```markdown
---
title: Books
permalink: /books/
kicker: Reading & marginalia
---
Your text here.
```

The header follows the order in the navigation file. Keep titles short so the menu remains comfortable on phones.

## Other edits

- Homepage: `_pages/home.html` (the prose is among the HTML tags).
- About: `_pages/about.md`.
- Social/contact links: `_data/elsewhere.yml`. Blank URLs stay hidden. Add `mailto:your-address` for Email. Add your Substack/profile URL when ready.
- CV: upload `cv.pdf` into `images/documents/`, then set the CV URL to `/images/documents/cv.pdf`. This location is public.
- Research page: `_work/debt-swaps.md`.
- Colours, spacing and typography: `_sass/_notebook.scss`.
- Site title, address and collections: `_config.yml`.

No browser JavaScript, third-party fonts, analytics, paid hosting or database are required. The original Academic Pages demo content has been removed. Unused theme components remain in the source for future use.

## Publishing setup (one time)

Use a public GitHub repository named `decodedhruv.github.io`. In **Settings → Pages → Build and deployment**, choose **Deploy from a branch**, then **master** and **/ (root)**. GitHub’s built-in Jekyll builder publishes each push. Keep Custom domain blank. HTTPS is automatic at the GitHub-provided address.

If publishing fails, open the latest run under **Actions → pages build and deployment** and read the failed step. You can run it again with **Re-run all jobs**.

## Local preview (optional)

With Ruby 3.3 and Bundler installed:

```sh
bundle install
bundle exec jekyll serve
```

Open http://localhost:4000. Changes to `_config.yml` require restarting the server.

## Credits

Based on Academic Pages, itself derived from Minimal Mistakes by Michael Rose. Original MIT licence retained in `LICENSE`.
