# Harari article-production workflow

Gregg can initiate this workflow by saying: **"Start the next Harari article."**

Follow `AGENTS.md` throughout. Use Hugo Extended 0.127.0 and PaperMod. Starting this workflow authorizes discovery, drafting, image creation, and local preview. It does not authorize committing or publishing. Explicit approval from Gregg is mandatory before committing or publishing the reviewed article and image.

This file contains permanent instructions and must not change during normal article creation. Read and update all article-specific progress, approval evidence, and coverage information in `history-notes/harari-progress.md`. Every instruction below to record or update state refers to that separate file.

## Resuming work

- Read the progress record and coverage ledger in `history-notes/harari-progress.md` before doing anything else. Resume an active article instead of selecting another transcript.
- Update `history-notes/harari-progress.md` after each completed phase and significant publication action. Record file paths, transcript segments, completed checks, blockers, and the next action. Keep drafted, reviewed, committed, and published states distinct.
- On resumption, inspect the current branch, Git status, article, image, and any recorded commit or remote state. Verify completed steps against their recorded evidence; repeat a step only if it is incomplete, its output is missing, or relevant inputs have changed.
- Reuse an existing article draft and generated image. Check whether the recorded Hugo server is still running before starting another. Do not repeat a commit, merge, or push that Git shows already succeeded.
- Record explicit approval with the approving message or chat reference and fingerprints of the reviewed article and image. Approval persists across interruptions for those exact versions. If approval cannot be established, or either reviewed file changes, return to local review and obtain explicit approval for the new versions.
- Record the next intended Git action before performing it and the resulting commit or remote evidence afterward. If interrupted between these updates, inspect Git to determine whether the action succeeded.
- `history-notes/harari-progress.md` is local workflow metadata. Never stage or commit it as part of an article publication. Do not include this permanent workflow, `AGENTS.md`, or other unrelated files in an article publication commit without separate explicit authorization.

## 1. DISCOVERY

- Confirm that the current branch is `backup-develop` before starting a new article. If it is not, stop and explain; do not switch branches automatically to begin discovery. When resuming an approved publication already on `main`, verify its recorded state and continue from that checkpoint.
- Inspect Git status, including staged and untracked files. Record the existing changes as the baseline and preserve them. Known unrelated changes are not permission to stage, overwrite, stash, or discard them.
- Compare the contents of `history-notes/` with existing Brief History articles in `content/posts/` and the coverage ledger. Match substance rather than titles, article lecture labels, or file counts. One article can cover multiple transcript segments; multiple articles can overlap one segment.
- Continue the established publication sequence unless Gregg explicitly requests an earlier gap. Read the current next transcript from `history-notes/harari-progress.md` and recheck coverage before selecting it rather than treating a previously recorded target as permanent.
- Maintain awareness of the earlier coverage gaps recorded in `history-notes/harari-progress.md`. Do not divert to an earlier gap without Gregg's request.
- Consult the sequence context in `history-notes/harari-progress.md` and account for existing overlaps when choosing the next article's scope.
- Record the chosen transcript or transcripts, proposed article scope, existing overlaps, and any uncertain matches. Do not assume each transcript needs its own article. Stop for guidance if uncertainty prevents a reliable selection.

## 2. ARTICLE CREATION

- Read the complete selected transcript or transcripts before drafting. Re-read relevant portions when revising claims.
- Examine existing Brief History posts for writing style, structure, YAML formatting, categories, tags, image placement, and links.
- Draft an original, accessible, accurate article in `content/posts/`. Summarize in original wording and attribute Harari's arguments appropriately.
- Preserve the distinction between Harari's arguments, hypotheses, interpretations, and established facts. Never invent quotations, lecture numbers, or historical claims.
- Include YAML front matter with a title, date, draft status, suitable categories and tags, a description, and the custom `post` field. Use the `Brief History` category and follow existing conventions.
- Link to relevant previous articles. Avoid repeating material already adequately covered; use a short recap and link when appropriate.
- Record the article path, intended URL slug, transcript coverage, and any unresolved questions. Ensure the article can be rendered in the local preview; do not treat its draft flag as publication approval.

## 3. IMAGE CREATION

- Generate one original historical illustration reflecting the transcript's central argument and actual substance. Never choose imagery solely from the lecture title or present the illustration as documentary evidence.
- Save the image in `static/image/` using a suitable descriptive filename. Preserve existing images; do not overwrite an unrelated asset.
- Reference it in the article as `/image/<filename>` and include accurate, descriptive alt text describing what is depicted.
- Inspect the result for relevance and consistency with the article. Record the image path and any remaining issues.
- If image generation is unavailable, pause, explain what is needed, and wait for Gregg's guidance. Do not silently substitute an unrelated image or advance past this phase.

## 4. LOCAL PREVIEW

- Start Hugo with this command, or reuse a verified server already serving this source in memory:

  ```sh
  hugo server --source /home/gregg/Projects/hugo --renderToMemory
  ```

- Do not modify `public/` for local previews. If a draft or future date prevents rendering, use the corresponding Hugo server inclusion flag while retaining `--renderToMemory`.
- Check that the article renders and that its image and internal links work. Provide Gregg with the actual localhost URL, normally `http://localhost:1313/posts/<slug>/`; use the server's actual port and generated route.
- Record the server details, article URL, review status, and fingerprints of the article and image. Wait for Gregg to inspect them.
- Allow revisions to both the article and image. Recheck changed output, update the fingerprints, and provide the revised preview for review.
- **Mandatory approval checkpoint:** do not commit, merge, or push until Gregg explicitly approves the reviewed article and image for publication. Silence, elapsed time, starting the workflow, and a revision request are not approval. If the approval's scope is unclear, clarify it before publication.

## 5. PUBLICATION

- Verify the recorded explicit approval still applies to the current article and image. Inspect Git status against the discovery baseline and stop if unexpected changes appear.
- Validate the production build with Hugo Extended 0.127.0, using a fresh temporary destination directory outside the repository. For example:

  ```sh
  hugo --source /home/gregg/Projects/hugo --destination <temporary-output-directory>
  ```

- Require a successful build and verify that the approved article, image, and links are present in the generated output. Production validation must not modify `public/`. If a correction changes the approved article or image, return to local review before committing it.
- Inspect local and remote branch state and the full difference that a push to `main` would deploy, including any existing unpublished commits. Verify that only approved changes will be published. Stop for guidance if unrelated or unapproved work would be included, branches have diverged unexpectedly, or branch switching would endanger local changes.
- On `backup-develop`, stage only the approved article and image using their explicit paths. Never stage or commit `history-notes/harari-progress.md` as part of an article publication. Never automatically stage `history-notes/`, and never use blanket staging for publication. Preserve unrelated staged changes; if they prevent an isolated commit, stop for guidance without unstaging them automatically.
- Inspect the staged diff and filenames. Commit only the approved article and image on `backup-develop`, then record the commit hash.
- Switch to `main` only as part of this approved publication. Merge the approved work from `backup-develop` into `main`, verifying the resulting changes and recording the merge or resulting branch commit.
- Push `main` to its verified deployment remote for Netlify deployment, and record the successful push and remote commit. Do not assume an attempted push succeeded.
- Stop on merge conflicts, unexpected changes, build failures, or rejected pushes. Explain the blocker and preserve the current state. Never force-push, reset away work, discard changes, or automatically resolve conflicts.
- When guiding Gregg through manual terminal operations, give one command at a time and inspect its result before the next command.

## 6. COMPLETION

- After the successful publication push, return to `backup-develop`. If a blocker prevents a safe return, report the actual branch and required next action instead of claiming completion.
- Verify Git status against the baseline. Preserve unrelated changes, `history-notes/`, and local workflow metadata; report any remaining changes accurately.
- Provide the live article URL under `https://maggodee.xyz/` using its verified route. Check deployment availability when possible and distinguish a pending deployment from a verified live page.
- Ask Gregg to confirm that the live article and image look correct. Record that confirmation as pending until Gregg responds; an automated check is not Gregg's confirmation.
- Record the exact transcript segment or segments covered, article path, live URL, publication commit, remote push evidence, and any partial coverage in the coverage ledger in `history-notes/harari-progress.md`. Mark coverage as published only after a successful publication push, and track live review separately.
- Update the next transcript in `history-notes/harari-progress.md` based on the published scope and a fresh coverage comparison. Keep the recorded earlier gaps visible. Leave any incomplete work and the next action explicit so another session can resume.
