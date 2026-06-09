# Project Instructions

## README Language Sync

- This repository uses `README.md` as the default Chinese profile page.
- This repository uses `README.en.md` as the English profile page.
- When changing profile content, update both files unless the change is language-specific.
- After editing either README, check that the two versions stay structurally aligned:
  - language switch links exist at the top of both files;
  - matching sections cover the same ideas;
  - project links, badge links, image URLs, and contact links stay in sync.

## Completion Workflow

- Before finishing any change, run relevant checks for the files touched.
- For README changes, run at least:
  - `git diff --check`
  - `rg -n "[ \t]+$" README.md README.en.md`
- If README image URLs are changed, verify the new URLs return `200` and an image content type.
- After checks pass, automatically commit the intended changes with a concise Conventional Commit message.
- After committing, automatically push the current branch to the remote.
- The GitHub HTTPS remote can be unreliable in this environment. If HTTPS push fails, use SSH over port 443:
  - `GIT_SSH_COMMAND='ssh -p 443 -o HostName=ssh.github.com -o StrictHostKeyChecking=accept-new'`
