We are going to migrate my existing academic website to the Jekyll **Minimal Light** theme:

https://github.com/yaoyao-liu/minimal-light

Do NOT redesign the content. Do NOT blindly convert the existing HTML into Jekyll.

The existing HTML website is the authoritative source for my content.
The Minimal Light theme will be the starting point for the new visual structure.

## Phase 1 — Inspect first

Before modifying any files:

1. Inspect the entire repository.
2. Read all existing HTML files.
3. Inspect the CSS, JavaScript, images, PDFs, and other assets.
4. Identify all existing pages and sections.
5. Identify:

   * biography/about content
   * research interests
   * publications
   * conferences
   * talks/presentations
   * collaborations
   * CV
   * contact information
   * external links
   * downloadable files
6. Identify repeated structures in the existing HTML.
7. Inspect the Minimal Light theme and understand its expected Jekyll structure and customization mechanisms.

Do not modify files during this phase.

After inspecting everything, briefly explain the migration plan before proceeding.

## Phase 2 — Migrate

Use Minimal Light as the basis of the new site.

The desired architecture is approximately:

```
_config.yml
_data/
    publications.yml
    conferences.yml
    talks.yml

_layouts/
_includes/

assets/
    css/
    images/
    files/

index.md
publications.md
conferences.md
research.md
cv.md
```

Adapt this to the actual Minimal Light theme instead of blindly following this example.

### Content

Extract my existing content from the HTML files.

Do not invent, remove, or alter factual information.

Preserve:

* names
* author lists
* publication titles
* venues
* years
* dates
* links
* DOI URLs
* PDF links
* code/project links
* conference information
* biography
* research information
* CV information
* contact information

## Publications

Make publications data-driven.

Prefer:

```
_data/publications.yml
```

Use a clean schema containing only fields that are actually needed.

For example:

```
- title: "..."
  authors: "..."
  venue: "..."
  year: 2026
  pdf: "..."
  code: "..."
  doi: "..."
```

Render these using a reusable Jekyll component/include.

If the existing repository contains BibTeX, inspect it and preserve it rather than duplicating information unnecessarily.

Do not introduce a database or client-side application.

## Conferences / talks

Convert conference and talk information into structured data where appropriate.

Use reusable Jekyll components to render them.

Preserve the existing ordering and factual information.

## Markdown vs HTML

Use Markdown for ordinary textual pages when it makes the site simpler.

Do NOT force everything into Markdown.

Custom HTML is explicitly allowed.

I want to retain the ability to create a page such as:

```
custom-page.html
```

with Jekyll front matter and arbitrary hand-written HTML.

## Theme customization

Use Minimal Light as the starting point, but customize it where necessary.

I want full control over:

* colors
* fonts
* typography
* spacing
* navigation
* homepage layout
* section layout
* publication layout
* conference layout
* responsive behavior

Prefer keeping customization in my repository rather than editing files inside an external dependency.

If the theme provides a layout or Sass/CSS component that needs modification, override/copy the relevant component into the project.

Do not treat the theme as immutable.

## Design direction

The new site should be:

* minimalist
* academic
* professional
* readable
* content-focused
* responsive
* visually clean

Do not add unnecessary:

* animations
* gradients
* dashboards
* cards everywhere
* interactive widgets
* frontend frameworks
* unnecessary JavaScript

The purpose of the website is to present my academic work, not to function as a web application.

## Existing assets

Preserve and correctly migrate all useful existing assets.

Pay particular attention to:

* images
* favicon
* PDFs
* CSS
* JavaScript
* internal links
* external links

Do not use absolute paths tied to my local filesystem.

Make paths work correctly with GitHub Pages and a custom domain.

## Jekyll / GitHub Pages

Set up the project so it can be run locally with:

```
bundle install
bundle exec jekyll serve
```

The generated website should be available at:

```
http://localhost:4000
```

Do not commit:

```
_site/
```

The Git repository should contain the Jekyll source, not generated output.

Keep dependencies minimal and compatible with GitHub Pages.

Do not introduce React, Vue, Next.js, Tailwind, Bootstrap, or another frontend framework.

## Custom domain

The site will eventually be deployed to GitHub Pages using my own registered domain.

Do not invent the domain name.

Configure Jekyll correctly for GitHub Pages, including URL/baseurl handling, but leave the actual domain as a placeholder if it cannot be determined from the repository.

## Validation

After the migration:

1. Run the Jekyll build locally.
2. Fix build errors and warnings where appropriate.
3. Verify every page.
4. Verify all internal links.
5. Verify all images.
6. Verify PDFs.
7. Verify publications.
8. Verify conferences/talks.
9. Verify the CV.
10. Verify the mobile/responsive layout.
11. Check that no existing content has been lost.

Compare the migrated site against the original HTML content.

## Git safety

Do not delete the original website until the migration has been validated.

If significant files need to be replaced, preserve them in Git history and explain what changed.

Do not commit changes automatically unless I explicitly ask you to commit.

## Important principle

Separate CONTENT from PRESENTATION.

Existing HTML:
authoritative content

Minimal Light:
starting presentation/layout

Jekyll:
mechanism connecting the two

The final result should make it easy for me to add a publication or conference by editing a simple data file rather than manually editing HTML.

Start with Phase 1 only. Inspect the repository and report your migration plan. Do not modify files yet.
