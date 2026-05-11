# Customize

Here we will give you some tips on how to customize the website. One important thing to note is that **ALL** the changes you make should be done on the **main** branch of your repository. The `gh-pages` branch is reserved for the generated website and should not be edited manually.

> **Note for users without coding experience:** You do **not** need to understand the technology stack or have any coding background to create and customize your own website with al-folio. This template is designed to be customizable without deep technical knowledge. Simply follow the instructions in this guide and you'll be able to create and customize your website!

## Quick Links

- [Project structure](#project-structure) - Overview of files and folders
- [Configuration](#configuration) - Main settings for your site
- [Creating content](#creating-new-pages) - How to add pages, posts, projects
- [Customizing style](#changing-theme-color) - Change colors and layout
- [Managing publications](#adding-a-new-publication) - Add academic papers

## Project Structure

The project is structured as follows, focusing on the main components that you will need to modify:

```
.
├── 📂 assets/: contains the assets that are displayed in the website
│   └── 📂 json/
│       └── 📄 resume.json: CV in JSON format (https://jsonresume.org/)
├── 📂 _bibliography/
│   └── 📄 papers.bib: bibliography in BibTeX format
├── 📂 _books/: contains the bookshelf pages
├── 📄 _config.yml: the configuration file of the template
├── 📂 _data/: contains some of the data used in the template
│   ├── 📄 cv.yml: CV in YAML format, used when assets/json/resume.json is not found
│   ├── 📄 repositories.yml: users and repositories info in YAML format
│   └── 📄 socials.yml: your social media and contact info in YAML format
├── 📂 _includes/: contains code parts that are included in the main HTML file
│   └── 📄 news.liquid: defines the news section layout in the about page
├── 📂 _layouts/: contains the layouts to choose from in the frontmatter of the Markdown files
├── 📂 _news/: the news that will appear in the news section in the about page
├── 📂 _pages/: contains the pages of the website
│   └── 📄 404.md: 404 page (page not found)
├── 📂 _posts/: contains the blog posts
├── 📂 _projects/: contains the projects
└── 📂 _sass/: contains the SASS files that define the style of the website
    ├── 📂 font-awesome/: contains the SCSS files for Font Awesome
    ├── 📄 _blog.scss: blog post, tags, and pagination styles
    ├── 📄 _components.scss: reusable component styles (cards, profiles, CV, projects)
    ├── 📄 _cv.scss: style of the CV page
    ├── 📄 _distill.scss: style of the Distill articles
    ├── 📄 _footer.scss: footer styles
    ├── 📄 _layout.scss: overall layout styles
    ├── 📄 _navbar.scss: navigation bar and dropdown menu styles
    ├── 📄 _publications.scss: publication list and bibliography styles
    ├── 📄 _tabs.scss: tabbed content styles
    ├── 📄 _teachings.scss: course and teaching styles
    ├── 📄 _themes.scss: theme colors and icons
    ├── 📄 _typograms.scss: typogram diagram styles
    ├── 📄 _typography.scss: text, headings, links, tables, and blockquote styles
    ├── 📄 _utilities.scss: utility styles (code highlighting, forms, modals, animations)
    └── 📄 _variables.scss: variables used in the SASS files
```

## Configuration

The configuration file [\_config.yml](_config.yml) contains the main configuration of the website. Most of the settings are self-explanatory and we tried to add as many comments as possible.

> Note that the `url` and `baseurl` settings are used to generate the links of the website, as explained in the [install instructions](INSTALL.md).

All changes made to this file are only visible after you rebuild the website. If you're running locally, restart `bundle exec jekyll serve`. If you've pushed to GitHub, the site will rebuild automatically.

### Checking Your Changes

If changes don't appear after refreshing, try:

- **Hard refresh** to reload the page ignoring cached content:
  - [Shift + F5 on Chromium-based browsers](https://support.google.com/chrome/answer/157179#zippy=%2Cwebpage-shortcuts)
  - [Ctrl + F5 on Firefox-based browsers](https://support.mozilla.org/en-US/kb/keyboard-shortcuts-perform-firefox-tasks-quickly)
- **Clear your browser cache** completely
- **Use a private/incognito session** to ensure no cached content:
  - [Chrome](https://support.google.com/chrome/answer/95464)
  - [Firefox](https://support.mozilla.org/en-US/kb/private-browsing-use-firefox-without-history)

## Modifying the CV Information

Your CV can be created using one of two formats. Choose the format that works best for you, or use both simultaneously by switching between them:

### RenderCV Format (Recommended)

[`_data/cv.yml`](_data/cv.yml) uses the [RenderCV](https://rendercv.com/) YAML format, which is human-readable and designed specifically for generating professional resumes.

**If you choose this format:**

1. Edit your CV data in [`_data/cv.yml`](_data/cv.yml)
2. Optionally customize how the PDF is styled by editing:
   - [`assets/rendercv/design.yaml`](assets/rendercv/design.yaml) — Design and styling
   - [`assets/rendercv/locale.yaml`](assets/rendercv/locale.yaml) — Localization and formatting
   - [`assets/rendercv/settings.yaml`](assets/rendercv/settings.yaml) — RenderCV settings
3. To display only this format, delete [`assets/json/resume.json`](assets/json/resume.json) (optional)

### JSONResume Format

[`assets/json/resume.json`](assets/json/resume.json) uses the [JSONResume](https://jsonresume.org/) standard format.

**If you choose this format:**

1. Edit your CV data in [`assets/json/resume.json`](assets/json/resume.json)
2. To display only this format, delete [`_data/cv.yml`](_data/cv.yml) (optional)

## Creating New Pages

You can create new pages by adding new Markdown files in the [\_pages](_pages/) directory. Copy an existing page and modify it. You can choose the layout in the frontmatter.

## Creating New Blog Posts

To create a new blog post, add a new Markdown file in the [\_posts](_posts/) directory. The filename must follow the format: `YYYY-MM-DD-title.md`

Example:

```
_posts/
├── 2026-05-11-my-first-post.md
└── 2026-05-12-another-post.md
```

## Creating New Projects

You can create new projects by adding new Markdown files in the [\_projects](_projects/) directory.

## Adding News

You can add news/announcements to the about page by adding new Markdown files in the [\_news](_news/) directory.

## Adding a New Publication

To add publications, create a new entry in the [\_bibliography/papers.bib](_bibliography/papers.bib) file. You can find BibTeX entries on Google Scholar or other academic databases.

### Author Annotation

In publications, your name is identified by the `scholar:last_name` and `scholar:first_name` arrays in [\_config.yml](_config.yml). For example:

```yaml
scholar:
  last_name: [Einstein]
  first_name: [Albert, A.]
```

Keep metadata about your co-authors in [\_data/coauthors.yml](_data/coauthors.yml).

## Changing Theme Color

A variety of beautiful theme colors have been selected for you. The default is purple, but you can quickly change it by editing the `--global-theme-color` variable in the [\_sass/\_variables.scss](_sass/_variables.scss) file.

## Customizing Layout and UI

You can customize the layout and user interface in [\_config.yml](_config.yml):

```yaml
back_to_top: true
footer_fixed: true
max_width: 930px
navbar_fixed: true
```

- `back_to_top`: Displays a "back to top" button in the footer.
- `footer_fixed`: When `true`, the footer remains fixed at the bottom of the viewport.
- `max_width`: Controls the maximum width of the main content area in pixels.
- `navbar_fixed`: When `true`, the navigation bar stays fixed at the top when scrolling.

## Adding Social Media Information

Social media information is managed through the [\_data/socials.yml](_data/socials.yml) file. Edit this file to add your social profiles.

The template supports icons from:

- [Academicons](https://jpswalsh.github.io/academicons/)
- [Font Awesome](https://fontawesome.com/)
- [Scholar Icons](https://louisfacun.github.io/scholar-icons/)

## Additional Resources

For more detailed information about customization, please refer to the [main documentation](README.md).
