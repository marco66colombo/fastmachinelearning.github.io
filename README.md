# Fast ML Lab Website Instructions
This website is built on GitHub Pages using Jekyll, and thus, editing raw HTML should be unnecessary for most content updates.

## Add a News Item

Create a file `_posts/yyyy-mm-dd-title.md` and add the following at the beginning:

```yaml
---
title: HLS4ML
external_link: https://fastmachinelearning.org/hls4ml/
layout: post
description: 'hls4ml: an open-source code framework for translating machine learning algorithms directly into FPGA firmware'
image: /images/hls4ml.png
---
```
 Note that file paths for images should include a leading `/` to indicate an absolute path from the root of the site. Putting quotes around the title/description (single or double) is recommended to avoid issues with yaml parsing. You can also add markdown content following this header and it will render as a complete web page, but as of yet there is no link to this post displayed on the front page, only content from the header. This may change in the future.

## Add an Application or Tool Gallery Entry

Application gallery entries live in `_applications/`. Tool gallery entries live in `_tools/`. Each entry is a Markdown file with YAML front matter and a longer writeup below it. Cards appear on the home page, and `layout: gallery-item` renders the entry's detail page.

The required fields for a future Google Form are title, summary, submitter, and domain. Optional fields include image, image alt text, affiliation, tools used, tags, review status, links, and long-form content. Optional blank fields should not break the website. See `docs/gallery-entry-template.md` for a complete starter template.

All CMS-managed images can live in `images/`. Reference image paths with a leading `/`, for example `/images/example.png`.

## Edit Content With Decap CMS

This repo includes a Decap CMS scaffold at `/admin/`. Decap is a Git-backed CMS: it edits Markdown and image files in this repository rather than using a database.

The CMS is configured in `admin/config.yml` for:

- Applications in `_applications/`
- Tools in `_tools/`
- News posts in `_posts/`
- Events in `_data/events.yml`
- Resources in `_data/resources.yml`

Required gallery fields are title, summary, submitter, and domain. Optional fields include image, image alt text, affiliation, tools used, tags, links, review status, and body content.

Before using this on production, configure GitHub authentication for Decap and confirm the backend repo/branch in `admin/config.yml`. This testing branch currently targets `marco66colombo/fastmachinelearning.github.io` on `master` through DecapBridge. For production, change `repo`, `branch`, and DecapBridge site settings to the FastML repository.

For GitHub-backed Decap CMS, editors must have write access to the configured repository. GitHub authentication also needs an OAuth/auth service, such as Netlify's GitHub authentication flow or another Decap-compatible OAuth provider. The `/admin/` page and content schemas are scaffolded here, but authentication still needs to be wired before non-local editing will work.

To test Decap locally, run the local backend proxy in one terminal:

```bash
npx decap-server
```

Then run the Jekyll site in another terminal:

```bash
jekyll serve
```

Open `http://127.0.0.1:4000/admin/`. With `local_backend: true`, Decap can edit files in the local working tree without GitHub authentication.


## Add a Person
In the file `_data/people/institution_name/lastf.yml` include the following:
```yaml
name: First Last
degree: Degree
field: Field
position: Current Position at Institution
interests: List of Interests
image: /images/lastf.png
external_link: http://your.url.here/
```
Note that the Jekyll site is set up to generate and alphabetize the institution list based on the folder names on the fly, interpreting an underscore in the directory name as a space. Therefore, if adding someone from a new institution, just add a new folder for their institution and place the person's info file inside. Note that file paths for images should include a leading `/` to indicate an absolute path from the root of the site.

## Add a Paper
Add papers to the yaml list in `_data/papers.yml`

Note that this will render markdown syntax. Putting quotes around the title (single or double) is recommended to avoid issues with yaml parsing.

**Example:**
```yaml
- 'Real-time Artificial Intelligence for Accelerator Control: A Study at the Fermilab Booster, [arXiv:2011.07371](https://arxiv.org/abs/2011.07371).'
```

## Add a Talk
Add talks to the yaml list in `_data/talks.yml`

Note that this will render markdown syntax. Putting quotes around the title (single or double) is recommended to avoid issues with yaml parsing.

**Example:**
```yaml
- "C. Herwig, An ML Control System for the Fermilab Booster, BIDS Machine Learning and Science Forum, April 2021, [abstract](https://bids.berkeley.edu/events/machine-learning-and-science-forum-2021-0405)"
```

## Add a Sponsor
Add sponsors to the yaml list in `_data/sponsors.yml`

Note that this will **not** render markdown syntax. Entries for both `name` and `image` fields are required (see example). Note that file paths for images should include a leading `/` to indicate an absolute path from the root of the site.


```yaml
- name: National Science Foundation
  image: /images/nsf.png
```

## Test the Site Locally
To test the site locally, install Jekyll along with the Jekyll github-pages extension (doing so via conda is recommended) and run the following command: `jekyll serve`

 This will start a local development web server to preview the site. Note that updating the config files may require restarting this server to take effect.
