# pr-test

This repository is used for testing the [sync-pr-to-gitlab](https://github.com/OpenSiFli/sync-pr-to-gitlab) GitHub Action, which synchronizes approved GitHub PRs to an internal GitLab instance.

## Overview

The `sync-pr-to-gitlab` action automates syncing of pull requests from GitHub to SiFli's internal GitLab. When a PR is approved and labeled, the action creates a corresponding branch and merge request on GitLab.

## How to trigger a sync

1. Open a pull request on this repository.
2. Add a comment with the format `sha=<commit-sha>` referencing the commit you want to sync.
3. Apply one of the following labels to trigger the sync workflow:
   - `PR-Sync-Merge` — merges the PR branch into the internal codebase.
   - `PR-Sync-Rebase` — rebases the PR onto the latest internal master branch.
   - `PR-Sync-Update` — updates an existing internal MR with new commits.

## Required secrets

| Secret | Description |
|---|---|
| `GITLAB_URL` | URL of the SiFli GitLab instance |
| `GITLAB_TOKEN` | Access token for GitLab API |
| `GIT_CONFIG_NAME` | Bot username for Git commits |
| `GIT_CONFIG_EMAIL` | Bot email for Git commits |

HalfSweet
reabse force