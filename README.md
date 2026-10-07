# Dhruva Nagesh — personal website

Built directly from Academic Pages using Jekyll, Markdown, Liquid, and Sass.
Live at https://decodedhruv.github.io. The custom domain is not connected.

## Edit the website

Open a file on GitHub, click the pencil, and choose **Commit changes**. GitHub Pages builds and publishes automatically from the `master` branch.

- Homepage: `_pages/home.html`.
- About: `_pages/about.md`.
- Header navigation: `_data/navigation.yml`. Writing goes to Substack; LinkedIn goes to the supplied profile.
- Elsewhere links: `_data/elsewhere.yml`. Blank URLs remain hidden.
- Styling: `_sass/_notebook.scss`.
- Portrait and form settings: `_data/profile.yml`.

## Add public work

Create `_work/project-name.md`:

```markdown
---
title: Project title
order: 3
kind: Game / article / collaboration / tool
selected: true
external_url: https://example.com/your-project
publication: Where it is hosted
description: "A short description."
tags: [philosophy]
---
```

`order` controls listing order. `selected: true` includes it on the homepage. The listing links straight to `external_url`. For a local project page, omit `external_url` and write Markdown beneath the second `---`. If you want a date displayed, add `date: 2026-10-07` and `show_date: true`.

Keep work that is not approved for public use out of this public repository. The previously displayed research project was removed from the current site/source, not from Git history.

## Writing

The header Writing link goes straight to Substack. Add newspaper articles to Public Work using the example above. To change the Substack address, update `_data/navigation.yml`, `_data/elsewhere.yml`, and the links in the homepage/About/Writing page.

## Add a portrait or photograph

Upload a photo under `images/`, then set `image: /images/your-photo.jpg` and descriptive `image_alt` text in `_data/profile.yml`. A portrait around 600 × 750 pixels works well. The placeholder disappears automatically.

For another photo in Markdown:

```markdown
![Describe what the image shows.](/images/your-photo.jpg)

*Your caption here.*
```

## Add a navigation item

Add to `_data/navigation.yml`:

```yaml
  - title: Gallery
    url: /gallery/
```

Create `_pages/gallery.md`:

```markdown
---
title: Gallery
permalink: /gallery/
---
Your text and images here.
```

For an external destination, use its full URL and `external: true`.

## Contact form

The complete accessible HTML form is `_includes/contact.html`. It includes first name, optional last name, email, and message fields, native browser validation, and a privacy notice. It needs no browser JavaScript.

Create a free Formspree form and verify its destination inbox. Put the supplied `https://formspree.io/f/...` endpoint in `contact_endpoint` in `_data/profile.yml`. Do not put passwords, API secrets, or private account data in the repository. While the endpoint is blank, the homepage provides a working LinkedIn contact link instead of a form that cannot deliver.

After activation, submit a test yourself and verify both Formspree’s confirmation and actual receipt in the inbox. A successful browser submission alone does not prove email delivery. Spam protection is managed in Formspree.

## Notes (available if needed later)

The Jekyll Markdown post system is retained, but the sample note has been removed and Notes is no longer in the menu. To add a post, create `_posts/YYYY-MM-DD-title.md` with title, date, tags, and Markdown content. Add a listing page/menu link when ready. Do not keep confidential drafts in a public repository.

## Hosting

GitHub **Settings → Pages → Deploy from a branch → master → / (root)**. Custom domain remains blank. Build status is under **Actions → pages build and deployment**.

## Credits

Adapted from Academic Pages, derived from Minimal Mistakes by Michael Rose. Original MIT license retained in `LICENSE`. Original theme components remain available in the source.
