# Repository guidance

This repository contains Sai Praneeth's LaTeX resume and static portfolio.
These instructions record established preferences. Follow newer explicit
user instructions when they change these defaults.

## Working approach

- Read the relevant files and current Git diff before editing. Preserve
  existing work, including staged changes.
- Use "resume" in communication.
- Use the current files for career facts and contact details.
- Delegate independent research or verification when useful. Keep simple
  edits small.
- For design work, study references and inspect the actual result before
  declaring it finished. Visual quality and readability matter.
- Distinguish reviews from requested edits. Report what changed and what
  was actually checked.
- Past permission to stage, commit, push, or deploy is not standing
  permission for later tasks.

## Resume content

- Preserve shared content across LaTeX, the generated PDF, and HTML when
  making content changes that apply to both formats. Keep presentation-only
  changes scoped to their medium.
- Preserve the reading order: header, Experience, Stacks, Education.
  Do not add About, Projects, Honors, or other sections unless requested.
- Preserve complete accomplishments and employer order during conversion.
  Do not silently summarize, omit, or hide bullets.
- Write concrete actions and outcomes. Remove filler without inventing
  ownership, technologies, metrics, or responsibilities.
- Preserve meaningful coordination and contribution qualifiers. For
  example, the pricing accomplishment must retain coordination with
  multiple teams and the outcome of consistent cross-page prices.
- Keep each metric attached to its original system. Different OCI region
  counts describe different systems.
- Preserve qualifiers such as "under", "approximately", and "contributed
  to". Use readable numeric forms such as "under 2 seconds".
- Keep the shared subtitle "Distributed Systems · Cloud · Fintech".
- Treat ATS recommendations as review findings until the user requests
  their application.

## LaTeX and PDF

- Edit SAI_PRANEETH_7YOE.tex, the relevant sections/*.tex files, or
  awesome-cv.cls. Never edit the PDF directly.
- The entry point includes experience, skills, and education. Projects
  and honors are currently excluded.
- Preserve the customized class conventions and ATS spacing fixes,
  including \atsSpace and \XeTeXinterwordspaceshaping.
- Rebuild the root PDF from the repository root with:

  ```sh
  docker run --rm -i --platform=linux/amd64 -w "/doc" -v "$PWD:/doc" thomasweise/texlive xelatex SAI_PRANEETH_7YOE.tex
  ```

- Preserve the one-page A4 layout unless a requested change requires
  otherwise. Check compilation, extracted text, and rendered output.
- For spacing changes, inspect the full page and the specific reported
  gap. Confirm the improvement is visible; changing the top margin alone
  does not establish that heading spacing is fixed.
- portfolio/SAI_PRANEETH_7YOE.pdf is a tracked relative symlink to the
  root PDF. Preserve it rather than creating a second maintained copy.

## Portfolio

- Keep website files inside portfolio/. Preserve the current standalone
  index.html with inline CSS and JavaScript. Use native browser features
  and avoid unnecessary dependencies, wrappers, or supporting files.
- Keep the site dark-only. Do not restore the light theme, theme toggle,
  section navigation, Website contact link, "sp." monogram, numbered
  section labels, or Pause/Regrow controls unless requested.
- Label the PDF link "PDF version", with a recognizable PDF icon.
  Do not restore a separate download control.
- Use recognizable GitHub and LinkedIn logos, short PDF-style dates,
  company-colored headings, and violet for HyperVerge.
- Use bold green for hiring-relevant impact and substantial engineering
  work. Use light blue for supporting emphasis and Stacks labels.
  Importance, rather than whether a phrase is technical, determines color.
- Preserve selective emphasis: HSM and UPI are emphasized while their
  expanded names remain regular text. Keep the education institution
  regular weight.
- Preserve dense, organic background branches that respond to pointer,
  touch, and scrolling without obscuring text. Create original artwork
  without reference-site credits or links. Do not copy code and strip
  required license notices.
- Keep content and PDF access usable without JavaScript. Preserve
  keyboard focus, mobile readability, reduced-motion support, print
  usability, and efficient loading on slow connections.
- Check relevant desktop and mobile layouts, overflow, links, PDF access,
  and interactions after changes. Keep temporary verification artifacts
  out of the deployment folder.
- Prefer headless Chromium using installed Playwright-compatible tooling
  for local portfolio verification. Check page structure and accessibility
  state, and inspect screenshots.
- If headless verification is unavailable, try browser integration. If
  that is unavailable, inspect `cua.getState()` for available browser
  applications and use `cua.getApp()` for native browser control. Open
  the preview in a new tab.
- Report browser verification as unavailable only after checking headless
  tooling, browser integration, and native app access.
- Reuse installed tooling. Keep browser dependencies and verification
  artifacts outside the repository.

## Preview and deployment

- GitHub Pages is the current deployment path. The workflow publishes
  portfolio/ automatically on pushes to master. Manual runs can deploy
  a selected branch containing the workflow.
- The deployment workflow does not compile LaTeX. Rebuild the root PDF
  before publishing resume source changes.
- Keep deployment instructions out of the website itself.
