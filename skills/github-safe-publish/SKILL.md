---
name: github-safe-publish
description: Safely use Git and GitHub in the local workspace for targeted publishing. Use when the user wants files or small project folders committed and pushed, when checking git status/remotes before publishing, when avoiding unrelated workspace changes, or when explaining/performing safe GitHub upload workflow in this environment. Covers inspection, staging scope, commit, push, verification, and safety constraints for minimal-risk GitHub operations.
---

# GitHub Safe Publish

Use this skill to publish files to GitHub safely from the local workspace.

## What this skill is for

Use this workflow when the user wants to:
- upload one file or a small project folder to GitHub
- check git status before pushing
- confirm which remote is configured
- avoid pushing unrelated dirty files
- make a minimal commit
- push safely and report the result
- understand the local GitHub workflow and its guardrails

## Core model

Treat GitHub publishing as a scoped operation, not a blanket sync.

Default posture:
- inspect first
- stage narrowly
- commit narrowly
- push only the intended change
- verify after push

## Required workflow

### 1. Inspect the repo first

Always check:
- `git status --short`
- `git remote -v`

If useful, also check:
- current branch
- staged diff
- unstaged diff for the intended file only

Do this before staging anything.

### 2. Define the publishing scope

Identify exactly what should be published:
- a single file
- a dedicated project folder
- a generated README or handoff file

If the workspace contains many unrelated changes, do not widen scope.

### 3. Place files deliberately

If the user wants the file grouped under a project, prefer:
- `projects/<project-name>/README.md`
- or another explicit path requested by the user

Prefer copying into the destination path instead of moving the original unless the user asks to move it.

### 4. Stage only the intended files

Use `git add <target-path>` only for the exact target.

Do not use broad staging patterns like:
- `git add .`
- `git add -A`

unless the user explicitly wants a full-repo publish and understands the impact.

### 5. Verify staged scope

Before commit, verify the index is narrow.

Check staged content with commands such as:
- `git diff --cached --stat`
- `git diff --cached --name-only`

If unrelated files are staged, unstage them before continuing.

### 6. Commit with a precise message

Use a boring, scoped commit message.

Good patterns:
- `Add <project-name> handoff`
- `Publish <file-name>`
- `Add project notes for <project-name>`
- `Add GitHub upload workflow skill`

Avoid vague commits like:
- `update`
- `misc changes`
- `fix stuff`

### 7. Push and verify

Push only after staged scope is confirmed.

After push, report:
- remote name
- branch
- commit hash
- destination path(s)
- whether the push succeeded

## Safety constraints

### Always avoid accidental bulk publish

Do not assume the user wants the whole workspace pushed.

If `git status` shows many unrelated files:
- keep the operation narrow
- publish only the requested file(s)
- do not clean up or reorganize unrelated files unless asked

### Do not hide repo state

If the repo is dirty, say so.
If the remote is missing, say so.
If push fails, say why.
Do not fake success.

### Do not overwrite intent

If the user asks to publish one file, do not silently include supporting files unless they are strictly required and the user would reasonably expect them.

### Prefer reversible structure changes

If the target needs a project folder, prefer creating a new folder and copying the file in.
That preserves the original source note and makes the publish path explicit.

## Local-environment assumptions

In this workspace, GitHub publishing typically means:
- use the existing git repo under the workspace
- inspect `origin`
- commit locally
- push to the configured remote

Do not assume every environment has the same remote or auth state. Always inspect first.

## How to explain this to the user

When the user asks how GitHub upload works here, explain it as:

1. check repo state
2. confirm remote
3. decide exact file scope
4. stage only that scope
5. verify staged diff
6. commit with a narrow message
7. push to origin
8. report commit hash and path

Keep the explanation practical, not academic.

## Standard output after success

Report:
- what was published
- where it lives in the repo
- commit hash
- remote/branch pushed

Example structure:
- published: `projects/example/README.md`
- commit: `abc1234`
- pushed to: `origin/master`
- result: success

## When not to proceed automatically

Pause and clarify if:
- the user has not identified what should be published
- multiple unrelated files could fit the request
- the remote looks wrong
- push would require broad staging
- the action would expose sensitive or unexpected files

## Minimal command pattern

Typical safe sequence:

1. inspect status and remotes
2. create/copy target file if needed
3. `git add <target>`
4. verify staged names
5. `git commit -m "<narrow message>"`
6. `git push origin HEAD`

Use this as the default path unless the user asks for something different.
