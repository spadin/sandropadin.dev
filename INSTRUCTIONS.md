You are a senior developer. Create a new Hugo static blog in this repo, configured for local preview and GitHub Pages deployment via GitHub Actions. Keep everything minimal and clean.

Requirements:

1) Hugo site:
- Use Hugo (extended).
- Select a modern, minimalist theme that is content-first and avoids loud visuals or heavy gradients.
- Clean typography, subtle color allowed, no flashy animations.
- Support syntax highlighting.
- Add basic navigation: Home, Posts, About.
- Content structure:
  - content/posts/
  - content/about.md
- Create at least one sample post:
  - content/posts/hello-world.md
  - Include front matter (title, date, draft=false)
  - Short example body text.

2) Local development:
- Ensure the site can be previewed locally using:
  - hugo server -D
- Add a README.md with:
  - Instructions to install Hugo on macOS using Homebrew
  - How to run the site locally
  - How to create a new post
- Ensure generated output is NOT committed:
  - Add public/ and resources/ to .gitignore
- Do not commit any built artifacts.

3) GitHub Pages deployment (GitHub Actions only):
- Create a GitHub Actions workflow at:
  - .github/workflows/deploy.yml
- The workflow must:
  - Run on push to main and on workflow_dispatch
  - Install Hugo (extended)
  - Use the official GitHub Pages actions:
    - actions/configure-pages
    - actions/upload-pages-artifact
    - actions/deploy-pages
  - Build using the baseURL output from configure-pages so it works for:
    A) User site: https://<username>.github.io
    B) Project site: https://<username>.github.io/<repo>
- In the README, note that GitHub Pages → Source must be set to “GitHub Actions”.

4) Configuration details:
- Use hugo.toml for configuration.
- Sensible permalinks for posts (e.g. /posts/:slug/).
- Enable GitHub-flavored Markdown.
- Enable syntax highlighting.

5) Theme handling:
- Prefer reliability over cleverness.
- You may use either:
  - a git submodule under themes/, or
  - Hugo Modules
- Ensure the chosen approach works in GitHub Actions without additional manual steps.

Deliverables:
- A working Hugo site scaffolded in the repo
- .github/workflows/deploy.yml
- README.md with clear setup and usage instructions
- Updated .gitignore
- Sample content as described above

IMPORTANT COMPLETION CONTRACT:
Once ALL steps above are completed successfully, print the following line as the FINAL OUTPUT, with no extra text after it:

=== HUGO_BLOG_SETUP_COMPLETE ===
