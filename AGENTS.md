# Repository Guidelines

## Project Structure & Asset Organization
`README.md` is the canonical gallery; every meme entry lives here as a heading, inline image, and optional link blockquote. Raw images sit in `README.assets/` and follow the `rednote-<sequence>.jpeg` naming pattern. Keep the folder flat—do not nest directories—so Git LFS is unnecessary and image links remain stable.

## Content Update Workflow
1. Drop the new meme into `README.assets/` and increment the numeric suffix (for example, `rednote-3-4.121.jpeg`).
2. Append a new `###` section to `README.md` with a concise Chinese title, the corresponding `![alt](README.assets/filename.jpeg)` embed, and the “查看小红书评论” quote linking to the source.
3. Preview the Markdown (`code README.md` or your editor’s preview) to confirm alignment and that the asset renders.

## Build, Test, and Quality Checks
This is a static docs repository. Run `npx markdownlint README.md` before opening a PR to catch spacing, heading, and list regressions. When you add or update external links, validate them with `npx markdown-link-check README.md` so the gallery does not accumulate dead references.

## Markdown Style & Naming Conventions
Use UTF-8 Markdown with two-space indentation where needed. Keep meme headings at `###`, bold only for emphasis, and prefer full-width punctuation to match existing copy. Alt text should mirror the heading, while blockquotes start with `> [查看小红书评论](...)` and include no trailing spaces. Image filenames stay lowercase, hyphenated, and sequential; avoid spaces or uppercase letters.

## Testing Guidelines
There are no automated tests, but every submission should include a manual preview screenshot or note in the PR confirming the image renders and the link resolves. If you replace an asset, ensure the old filename is removed and not orphaned in git history.

## Commit & Pull Request Guidelines
Follow the short, conventional commit style in history (e.g., `docs: refresh gallery layout`). Group related meme additions into a single commit. PRs should describe the number of entries touched, link back to the originating 小红书 post, and mention any cleanup performed in `README.assets/`. Screenshots are welcome when adjusting formatting or layout.
