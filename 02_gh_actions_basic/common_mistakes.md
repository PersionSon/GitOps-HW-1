# Common Mistakes & Fixes

1. **Workflow not visible in the Actions tab**
   - Cause: File is not in `.github/workflows/` or wrong extension.
   - Fix: Move the file to `.github/workflows/` and make sure it ends with `.yml` or `.yaml`.

2. **YAML invalid**
   - Cause: Wrong indentation or tabs instead of spaces.
   - Fix: Use 2 spaces per indent level; validate at https://yamlchecker.com.

3. **No access to repo files**
   - Cause: `actions/checkout` step is missing.
   - Fix: Add `- uses: actions/checkout@v4` as the first step.

4. **Secret is empty (for later sections)**
   - Cause: Repository secret not defined.
   - Fix: Go to Settings → Secrets and variables → Actions → New repository secret.
