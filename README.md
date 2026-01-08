# sandropadin.dev

A minimal Hugo blog using the PaperMod theme, configured for local development and GitHub Pages deployment.

## Prerequisites

### Install Hugo on macOS

Install Hugo extended version using Homebrew:

```bash
brew install hugo
```

Verify the installation:

```bash
hugo version
```

Ensure you have Hugo extended (the version should include "extended").

## Local Development

### Clone the Repository

```bash
git clone --recursive <repository-url>
cd <repository-name>
```

> **Note**: The `--recursive` flag ensures the theme submodule is cloned as well.

If you already cloned without `--recursive`, initialize the submodule:

```bash
git submodule update --init --recursive
```

### Run the Site Locally

Start the Hugo development server with drafts enabled:

```bash
hugo server -D
```

The site will be available at `http://localhost:1313/`. The server will automatically reload when you make changes.

### Create a New Post

Create a new post using Hugo's archetype:

```bash
hugo new posts/my-new-post.md
```

This creates a new file at `content/posts/my-new-post.md` with front matter. Edit the file and set `draft: false` when ready to publish.

## GitHub Pages Deployment

This site is configured for automatic deployment to GitHub Pages using GitHub Actions.

### Setup Instructions

1. Push this repository to GitHub

2. Go to your repository's **Settings** > **Pages**

3. Under **Build and deployment**, set **Source** to **GitHub Actions**

4. The site will automatically deploy when you push to the `main` branch

### How It Works

The GitHub Actions workflow (`.github/workflows/deploy.yml`):
- Triggers on push to `main` or manual dispatch
- Installs Hugo extended
- Builds the site with the correct base URL (works for both user and project sites)
- Deploys to GitHub Pages using official actions

The workflow automatically detects the correct base URL:
- **User site**: `https://<username>.github.io`
- **Project site**: `https://<username>.github.io/<repo>`

## Project Structure

```
.
├── archetypes/         # Content templates
│   └── default.md
├── content/            # Site content
│   └── posts/
│       └── hello-world.md
├── layouts/            # Custom layouts (empty by default)
├── static/             # Static files (images, etc.)
├── themes/             # Hugo themes
│   └── PaperMod/       # Theme submodule
├── .github/
│   └── workflows/
│       └── deploy.yml  # GitHub Actions workflow
├── hugo.toml           # Hugo configuration
├── .gitignore          # Git ignore rules
└── README.md           # This file
```

## Configuration

The site configuration is in `hugo.toml`. Key settings include:

- **Theme**: PaperMod (minimalist, content-first)
- **Syntax highlighting**: Enabled with Monokai style
- **Permalinks**: Posts use `/posts/:slug/` format
- **Markdown**: GitHub-flavored Markdown enabled
- **Navigation**: Home, Posts

## License

Content and configuration are provided as-is. The PaperMod theme has its own license.
