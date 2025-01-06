# Mandy's Daily Commit

This repository is configured to use a GitHub Actions workflow for automated daily commits. The workflow ensures a file named `commit_number.md` is updated every day. If the file does not exist, it creates the file with an initial commit number. If it already exists, the commit number is incremented by 1.

## Workflow Overview

### Process

1. **Checkout Repository**:

   - Clones the repository to the runner.

2. **File Operations**:

   - Checks if `commit_number.md` exists.
   - If it does not exist:
     - Creates the file.
     - Writes the initial content with commit number 1.
   - If it exists:
     - Reads the current commit number.
     - Increments the commit number by 1.
     - Updates the file.

3. **Git Configuration**:

   - Sets user name and email for committing changes.

4. **Commit and Push**:
   - Adds the file to Git, commits the changes, and pushes them back to the repository.

## File Details

### `commit_number.md`

- This file contains:
  - A greeting message.
  - The current commit number.

#### Example Content:

If the file is created:

```
Hello, my name is Mandip Kumar Kanu
commit number: 1
```

If the file already exists, and the last commit number is 5, it updates to:

```
Hello, my name is Mandip Kumar Kanu
commit number: 6
```

## GitHub Actions Workflow

### Workflow File Location

- Path: `.github/workflows/commit.yml`