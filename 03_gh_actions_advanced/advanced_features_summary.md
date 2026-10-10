# Advanced Features Summary

- **Docker build in GitOps**: CI builds the Docker image and tags it with the Git SHA. The GitOps controller (e.g., Argo CD) later pulls this exact image tag to deploy.
- **needs / if**: `needs` creates a dependency (e.g., deploy waits for build). `if` adds conditional logic (e.g., only deploy to production on the `main` branch).
- **matrix**: Runs the same job multiple times with different configurations (e.g., Node 18 and Node 20) in parallel.
- **environment approval**: Pauses the workflow until a human manually approves the deployment (used for `production`).
