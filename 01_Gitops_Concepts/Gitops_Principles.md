## SomeThings I Undrestan About GitOps:

   -GitOps Means You Write How Your Apps And Servers Should Look In A Git Repo  
           Then A Tool Automatically Makes The Real System Match What Git Says.

## What's Declarative:

   -You Write Down What You Want The System To Look Like, Not The Steps To Build It
        The Tool Figures Out How To Make It Happen.

## What's Versioned & immutable:

   -Every Change Is Saved As A New Version In Git, So Old Versions Are Never Edited
       You never change the live system by Hand; Git Is The Only Source Of Truth.

## What's Pulled Automatically: 

   -An Agent Inside The System Checks Git For Changes On Its Own
        You Don’t Push Changes From Outside; The System Pulls Them In.


## What's Continuosly Reconcilled:

   -The Agent Keeps Comparing The Real System With What Git Says It Should Be.
        If They Don’t Match, It Automatically Fixes The Real System To Match Git Again.


## Defrent Between  CI/CD And GitOps (Focuse/Example Tools):


     | Practice | Main Focus | Example Tools |
|---|---|---|
| **CI (Continuous Integration)** | Automatically build, test, and merge code changes often to catch problems early. | GitHub Actions, GitLab CI, Jenkins, CircleCI |
| **CD (Continuous Delivery/Deployment)** | Automatically deliver or deploy tested code to staging/production. Delivery = ready to release; Deployment = released automatically. | Argo CD, Spinnaker, Jenkins, GitLab CD, Tekton |
| **GitOps** | Use Git as the single source of truth for declarative apps/infra; a pull-based agent continuously reconciles the cluster with Git. | Argo CD, Flux, Rancher Fleet |



## If SomeOne Change Manually On Cluster For Example (KubeCtl Scale) In Pull Model How We Can Find And Edit ??


   -The Agent Continuously Compares The Live Cluster State With The Desired State In Git.
        If Someone Manually Scales With KubeCtl, The Agent Detects This Drift.
        It Then Automatically Reverts The Cluster To Match Git, Undoing The Manual Change.