# Secrets Notes

**Why we don't echo secrets:**
GitHub Actions automatically masks secrets in logs (replaces them with `***`). However, it is still a best practice to never print secrets directly. If a secret is accidentally transformed (e.g., Base64 encoded) and printed, it might bypass the mask. We only print the length `${#MY_API_TOKEN}` to verify it exists without exposing the value.
