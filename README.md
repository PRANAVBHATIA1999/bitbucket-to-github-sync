# bitbucket-to-github-sync

This project automates the **synchronization of public repositories** from **Bitbucket to GitHub** using **Bitbucket Pipelines**. It ensures that all branches, tags, and commits are mirrored, keeping GitHub up to date with changes in Bitbucket.

---

## Features

**Sync Public Repositories Only** – Automatically filters public repositories from Bitbucket.  
**Auto-Create GitHub Repositories** – Creates the repository in GitHub if it doesn’t exist.  
**Full Repository Mirroring** – Uses `git push --mirror` to sync **branches, commits, tags, and deletions**.  
**Secure Authentication** – Uses **Bitbucket App Passwords** and **GitHub Personal Access Tokens (PATs)**.  
**Fully Automated** – Runs as a **Bitbucket Pipeline**, no manual intervention needed.  

---

## Use Cases

**Migrate Open Source Projects** – Maintain a presence on both Bitbucket & GitHub.  
**Automate Repository Syncing** – Ensure GitHub stays updated without manual pushes.  
**Increase Project Visibility** – Open source projects get better reach on GitHub.  

---

## Setup Instructions

### 1. Generate Required Access Tokens
Before using the pipeline, create and store these tokens:

### Bitbucket Variables (Add to Bitbucket Repository Variables)
- `BITBUCKET_USERNAME` → Your Bitbucket username.
- `BITBUCKET_APP_PASSWORD` → [Generate a Bitbucket App Password](https://bitbucket.org/account/settings/app-passwords/)  
  - **Required Permissions:** `Repository Read`, `Repository Write`, `Account Read`
- `BITBUCKET_WORKSPACE` → Your Bitbucket **workspace ID**.

### GitHub Variables (Add to GitHub)
- `GITHUB_USERNAME` → Your GitHub username.
- `GITHUB_TOKEN` → [Generate a GitHub PAT](https://github.com/settings/tokens)  
  - **Required Scopes:** `repo`, `admin:repo_hook` *(optional for webhooks)*
- `GITHUB_ORG` *(Optional)* → If pushing to a GitHub organization instead of a personal account.

## References

This pipeline was built using best practices from official documentation and API references:

1. **Bitbucket API - Fetching Public Repositories**  
   - [Bitbucket Cloud API - Repository Endpoint](https://developer.atlassian.com/bitbucket/api/2/reference/resource/repositories/%7Bworkspace%7D)  

2. **Bitbucket Pipelines - Variables & Secrets**  
   - [Bitbucket Pipelines - Environment Variables](https://support.atlassian.com/bitbucket-cloud/docs/variables-and-secrets/)  

3. **GitHub CLI (`gh`) - Managing Repositories**  
   - [GitHub CLI Documentation](https://cli.github.com/manual/)  

4. **Git Commands for Pushing & Mirroring**  
   - [Git Push Documentation](https://git-scm.com/docs/git-push)  

5. **Bitbucket App Passwords - Authentication Guide**  
   - [Bitbucket App Passwords](https://bitbucket.org/account/settings/app-passwords/)  

These references ensure that the pipeline follows **official documentation and best practices** for a fully automated sync between Bitbucket and GitHub.

---
