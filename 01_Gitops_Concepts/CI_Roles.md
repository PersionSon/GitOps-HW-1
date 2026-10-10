## CI produces artifacts and commits manifest changes. It never runs kubectl apply and Never      Holds  Cluster Credentials


## Block A – Build: CI compiles code and builds a Docker image.

## Block B – Push: CI pushes the image to a registry with a unique tag (use Git SHA, e.g.   sha-abc123, never latest).

## Block C – Update manifest: CI commits the new image tag into the GitOps repo (deploy/overlays/prod/kustomization.yaml).

## Block D – Handoff: GitOps controller (Argo CD / Flux) detects the commit and applies it. CI's job ends here.

Code Repo                         GitOps Repo                 Cluster
┌─────────┐   build+push   ┌──────────────┐  update tag  ┌──────────────┐
│  src/   │───────────────▶│ registry:    │─────────────▶│ deploy/      │
│         │                │ app:sha-abc  │  (git commit)│ manifests    │
└─────────┘                └──────────────┘              └──────┬───────┘
                                                                │ pull
                                                                ▼
                                                        ┌──────────────┐
                                                        │ Argo CD/Flux │
                                                        │  reconciles  │
                                                        └──────────────┘

Rule: CI = build + push + update manifest
      GitOps controller = the ONLY thing that applies to cluster

