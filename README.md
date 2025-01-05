
# Automated Daily Commits with GitHub Actions

This project demonstrates how to use GitHub Actions to perform automated daily commits to a repository. The workflow is designed to update a file named `commit_number.md` every day at midnight UTC, incrementing a commit counter and pushing the changes back to the repository.

## Features
- **Automated Workflow**: Runs daily at midnight (UTC) using GitHub Actions.
- **Incremental Updates**: Maintains a file (`commit_number.md`) with an incrementing commit counter.
- **Fully Configurable**: Easy to customize the workflow and schedule.

---

## How It Works
1. **Daily Trigger**:
   - The workflow runs every day at midnight UTC, scheduled using a cron job.

2. **File Management**:
   - If the file `commit_number.md` does not exist, it creates the file with:
     ```
     Hello, this is an automated file.
     Commit number: 1
     This is part of an **automated daily commit** performed by a **GitHub Actions workflow**.
     ```
   - If the file already exists, it reads the current commit number, increments it, and updates the file.

3. **Git Configuration and Push**:
   - Configures Git with a name and email.
   - Pushes the updated file back to the repository.

---

## File Structure
```
.
├── .github/
│   └── workflows/
│       └── commit.yml      # Defines the GitHub Actions workflow
├── commit_number.md        # File updated and committed daily
└── README.md               # Project documentation
```

---

## Example Output
Here’s an example of how `commit_number.md` might look after a few commits:

```
Hello, this is an automated file.
Commit number: 3
This is part of an **automated daily commit** performed by a **GitHub Actions workflow**.
```

---

## Configuration
1. **Workflow File**:
   The workflow is defined in `.github/workflows/commit.yml`. You can customize the schedule or file content there.

2. **Schedule**:
   The workflow runs daily at midnight UTC using this cron expression:
   ```yaml
   schedule:
     - cron: '0 0 * * *'
   ```

3. **GitHub Token**:
   The workflow uses the `secrets.GITHUB_TOKEN` to securely authenticate and push changes to the repository.

---

## Usage
1. Clone or fork this repository.
2. Ensure the `.github/workflows/commit.yml` file is added to your repository.
3. Push the changes to GitHub.
4. The workflow will start running automatically.

---

## Notes
- Ensure that GitHub Actions is enabled for your repository.
- To customize the commit file content or schedule, modify the `commit.yml` file.

---
