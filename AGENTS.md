# Project instructions

These instructions govern the production of articles about Yuval Noah Harari's lectures for https://maggodee.xyz/.

## Project

- Use Hugo Extended 0.127.0 with the PaperMod theme.
- Work on `backup-develop`. The publishing branch is `main`.
- Lecture transcripts are in `history-notes/`.
- Articles are in `content/posts/`.
- Images are in `static/image/`.
- Follow the formatting and writing conventions of existing Brief History posts.

## Article production

- Whenever Gregg requests a new Harari article, including "Start the next Harari article," follow `ARTICLE-WORKFLOW.md` and resume any recorded work before starting another article. Its approval checkpoints are mandatory.
- Compare transcripts with existing posts to identify unpublished material.
- Never assume every transcript requires a separate article. An article may draw on multiple transcript segments, and an existing post may already cover a segment.
- Read the complete relevant transcript or transcripts before drafting.
- Write accessible, accurate summaries in original wording.
- Attribute Harari's arguments appropriately.
- Distinguish hypotheses, interpretations, and established facts.
- Never invent lecture numbers, quotations, or historical claims.
- Include YAML front matter with a title, date, draft status, appropriate categories and tags, a description, and the custom `post` field, following existing posts.
- Include relevant links to previous articles.

## Images

- Create an original illustration representing the lecture's actual substance.
- Never select imagery based solely on the lecture title.
- Use descriptive alt text.
- Store article images in `static/image/` and reference them in Markdown as `/image/<filename>`, consistent with existing posts.
- If image generation is unavailable, stop and explain what is needed to proceed.

## Local review

- Preview using:

  ```sh
  hugo server --source /home/gregg/Projects/hugo --renderToMemory
  ```

- Do not modify `public/` for local previews.
- Allow Gregg to inspect the article and image and request revisions.
- Never commit or publish an article without explicit approval from Gregg.

## Publication

- Require explicit approval from Gregg before any publication.
- After approval, validate the production build. Use a temporary output directory so validation preserves existing files and unrelated changes.
- Stage only the approved article and image. Do not include unrelated files or previously staged changes in the commit.
- Commit on `backup-develop`.
- Merge into `main` and push for Netlify deployment. Check the changes that would be published before proceeding; stop if they include unapproved work.
- Never force-push or discard existing changes.
- Return to `backup-develop` afterward.
- Ask Gregg to verify the live article.

## Safety

- Preserve all existing articles and unrelated changes.
- Preserve `history-notes/` and all its contents.
- Never automatically stage `history-notes/`.
- Stop if Git reports unexpected changes or merge conflicts, and explain the situation to Gregg before proceeding.
- Use one command at a time when guiding Gregg through manual terminal operations.
- Require explicit approval before any publication.
