---
name: finishing-a-development-branch
description: Use when implementation is complete to verify tests pass, then hand off to user for merge/PR decisions
---

# Finishing a Development Branch

## Overview

Verify tests pass and inform the user that development is complete. The user will handle merge/PR decisions manually.

**Core principle:** Verify tests → Report status → Hand off to user.

**Announce at start:** "I'm using the finishing-a-development-branch skill to verify this work is complete."

## The Process

### Step 1: Verify Tests

**Run the project's test suite:**

```bash
# Run project's test suite
npm test / cargo test / pytest / go test ./...
```

**If tests fail:**
```
Tests failing (<N> failures):

[Show failures]

Development is not complete. Please fix these issues.
```

Stop. Do not proceed to Step 2.

**If tests pass:** Continue to Step 2.

### Step 2: Report Completion

Inform the user:

```
Development complete. All tests passing.

Commits on this branch:
[git log --oneline output]

Files changed:
[git diff --stat output]

You can now:
- Create a Pull Request manually
- Merge to your base branch
- Keep the branch for further work
```

## Red Flags

**Never:**
- Skip test verification
- Claim work is complete when tests fail
- Attempt to merge, push, or create PRs automatically

**Always:**
- Verify tests before reporting completion
- Show the user what was changed (commits and files)
- Let the user decide next steps
