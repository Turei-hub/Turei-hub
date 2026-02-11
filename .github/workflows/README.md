# PR Review Workflow

This GitHub Actions workflow automatically monitors pull requests and generates comprehensive review reports.

## Features

- **Automatic Triggering**: Runs automatically when PRs are opened, synchronized, or reopened
- **Change Analysis**: Analyzes all changed files in the pull request
- **Statistics**: Provides detailed statistics including:
  - Number of files changed
  - Lines added
  - Lines deleted
  - File-by-file breakdown
- **Automated Reporting**: Posts a comprehensive report as a comment on the PR
- **Smart Updates**: Updates existing comments instead of creating duplicates

## How It Works

1. **Checkout**: Fetches the repository with full history
2. **Get Changed Files**: Identifies all files modified in the PR
3. **Analyze Changes**: Computes statistics about additions and deletions
4. **Generate Report**: Creates a markdown-formatted report
5. **Post Comment**: Adds the report as a PR comment (or updates existing comment)
6. **Summary**: Adds a summary to the GitHub Actions workflow run

## Report Contents

Each report includes:

- PR number and title
- Author information
- Source and target branches
- List of changed files
- Detailed statistics
- Line-by-line change summary

## Permissions

The workflow requires:
- `pull-requests: write` - To post comments on PRs
- `contents: read` - To read repository contents

## Usage

The workflow runs automatically. No manual intervention is required.

To disable it, delete or rename the `.github/workflows/pr-review.yml` file.

## Example Report

```markdown
## 📊 Pull Request Review Report

**PR #123**: Add new feature

### 📝 Summary
- **Author**: @username
- **Branch**: `feature-branch` → `main`
- **Files Changed**: 5
- **Lines Added**: 150
- **Lines Deleted**: 20

### 📂 Changed Files
...

### 📈 Statistics
...

### ✅ Review Status
- Changed files have been analyzed
- Statistics have been generated
- Report has been created
```
