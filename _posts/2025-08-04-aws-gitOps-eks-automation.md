---
title: "AWS: GitOps for Amazon EKS Automation"
author: Kleiner
categories: [Amazon Web Service]
tags: [GitOps, Kubernetes, Flux, Argo CD]
render_with_liquid: false
media_subpath: /images/aws/gitOps_eks
image:
  path: aws_skill_builder.webp
---

[![AWS Educate Room Link](aws_skill_builder.webp){: width="600" height="300" .shadow}](https://skillbuilder.aws/learn/KB9MZUXHSF/gitops-for-amazon-eks-automation/52PNE2AN58){: .center }

## What is GitOps?
GitOps is an approach where infrastructure is defined as code (IAC) alongside application code, versioned in a git repository, and then provisioned following the same merge request as application software code.
1. Infrastructure as Code
  : hosted just like software code
2. Git
  : versioning and pull requests workflows
3. CI/CD
  : for automated build, test and deploy

## GitOps Principles
1. A system managed by GitOPs must have its desired state expressed declaratively. When the application's configurations are defined dclaratively, Git can be relied as the Single Source of Truth. 
2. Desired state is stored in a way that enforces immutability, versioning and retains a comlplete version history
3. Approved hanges can be automatically applied
4. Software agents continuously observe actual system state and attempt to apply the desired state

## Pull vs Push Pipeline
GitOps Pull based Pipeline working model
- A push-based piepline means that code starts with the CI system to push any changes to the Kubernetes cluster.

A deployment pipeline will push changes from Git to the infrastructure when code is updated. For example, when some code is merged with the main branch in Git, the Continuous Delivery Pipeline will then update and deploy the Kubernetes cluster with the new deployment. A Git change triggers the pipeline that pushed to the infrastructure. 

- A pull-based pipeline uses deployment Automator, which is responsible for watching the image registry and a Deployment Synchronizer residing in the cluster to maintain its state.

Agents running in the Kubernetes cluster will constantly monitor the main Git repository for any changes. When changes are detected, these agents will pull the updates to make the running cluster reach the desired state.

## Best Practices for GitOps
1. **The Principle of Declarative Configuration**
: This means the desired system state is declared in files. The common supported formats are `JSON` or `YAML`. These files are also versioned controlled.

2. **The Principle of Immutable Configuration Versions**
: Any changes will be reserved in a new version via Git commit. Instead of making changes directly to a running instance, updates or new features are delivered by creating a new, updated version of the system and replacing the old one.

3. **The Principle of Continuous State Reconciliation**
: The system is continuously monitored and automatically reconciled to match the declared state in Git. 

4. **The Principle of Operations Through Declaration**
: All operations are updated by changing declaration and letting reconcilation happens.

## GitOps On IAC
Kubernetes is managed almost entirely on declarative configurations and because containers are immutable.

### Managing CLusters with GitOps
In GitOps, each cluster's desired state is declared in a separate Git Repository or Git Branch. The GitOps Agent like **Flux** is deployed in each cluster. It monitors the relevant Git repository for that particular cluster. When a change is made, for example, an updated `YAML` configuration, a **pull request** is triggered. It is then reviewed and merged to the branch.

The Flux tool in the **Developer** cluster detects the Git Commit and automatically apply the change to sync the live state. Meanwhile, the Flux in **Production** cluster will ignore the commit as it is monitoring the **Production** cluster's branch. To bring over the changes from the **Dev** cluster to the **Prod** cluster, we have to merge these branches.

### Multi-Tenant Clusters
When running muliple tenants on a shared Kubernetes cluster, isolation and security are crucial. We need to ensure that each tenant can't access or impact each other. 

By having separate repository for each tenant, we maintain configuration isolation. The GitHub Operator like Flux in each namespace can monitor the appropriate repository.

## GitOps Toolkits
1. Flux is part of the CNCF and designed to be modular and Kubernetes-native. It continuously monitors Git repositories and applies changes to the cluster using Kubernetes controllers. It supports:
- Multi-tenancy via GitRepository and Kustomization resources.
- Progressive delivery using Flagger for canary and blue-green deployments.
- Secure operations, as it pulls changes rather than requiring Git access from the cluster.

2. Argo CD is a declarative, GitOps continuous delivery tool with a rich web UI, CLI, and REST API. Key features include:

  - Visual diffing and syncing between Git and live state.
  - Health and status assessment of resources.
  - RBAC, SSO integration, and multi-cluster support.

3. Kustomize is a configuration manager for Kubernetes objects. Leveraging layering (overlaying) to preserve the base settings of the application. Kustomize settings are defined in a `kustomization.yaml` file. Kustomize also allows you to scale easily by resuing a base file accross all your environments (development, production, staging, etc.) and then overlay specifications for each. 
