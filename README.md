# FastML Website Content Editing

This website is built on GitHub Pages with Jekyll, but the main editing path is now the Decap CMS admin panel rather than direct code edits.

## Preferred Workflow

Use the Decap CMS at `/admin/` to add, update, or remove website content. This is the intended path for routine content work because it lets people update the site quickly without needing to work directly in the codebase.

The CMS currently manages:

- News
- Events
- Resources
- Applications
- Tools

Collaboration, governance, sponsors/partners, and contact are still managed directly in code.

## Access

Editing through the CMS requires an invite link and access to the configured DecapBridge/GitHub setup.

Marco Colombo is currently managing CMS invites. Reach out to:

- `colombo.marco24@gmail.com`
- `mcolom4@illinois.edu`

## How It Works

Decap is a Git-backed CMS. Editors work in the browser, and the CMS writes Markdown, YAML, and image changes back to the repository. GitHub Pages then rebuilds the website.

This keeps the site static and version-controlled, while avoiding the need for most editors to work directly with Git or Jekyll.

## Direct Code Editing

It is still possible to edit content directly in the repository. This is the fallback path, not the preferred one.

Main content locations:

- News: `_posts/`
- Events: `_data/events.yml`
- Resources: `_data/resources.yml`
- Applications: `_applications/`
- Tools: `_tools/`
- Images: `images/`

If you edit content directly, use leading `/` paths for images, for example `/images/example.png`.


## Local CMS Testing

To test the CMS locally, set `local_backend: true` in the config you are using and start the Decap local backend proxy:

```bash
npx decap-server
```

Then start the Jekyll site:

```bash
jekyll serve
```

Open:

```text
http://127.0.0.1:4000/admin/
```

## Decap Config

- `admin/config.yml`: production config for `fastmachinelearning/fastmachinelearning.github.io`
