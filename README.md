# gitops-hw-01

- Homework Repository For GitOps Course

# 02 - GitHub Actions Basic CI

This folder contains a basic GitHub Actions workflow that:
- Runs on every push and pull request to `main` or `master`
- Checks out the code
- Prints environment info (repo, branch, actor, commit, event)
- Runs a smoke test to verify `README.md` exists