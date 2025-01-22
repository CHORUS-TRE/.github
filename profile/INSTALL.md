# CHORUS-TRE Installation
## Table of contents
<!-- Generated with VIM plugin https://github.com/mzlogin/vim-markdown-toc -->
<!-- vim-markdown-toc GFM -->

* [Prerequisites](#prerequisites)
    * [Local machine tools](#local-machine-tools)
    * [Infrastructure](#infrastructure)
* [Installation](#installation)
    * [Bootstrap](#bootstrap)
    * [Secrets](#secrets)
    * [Deploy](#deploy)

<!-- vim-markdown-toc -->

## Prerequisites

### Local machine tools
| Component                                                          | Description                                                                                                                                                                                                      |
| ------------------------------------------------------------------ | ---------------------------------------------------- |
| [git](https://git-scm.com/downloads)                               | Git is required to clone this repository             |
| [kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl)  | Kubernetes command-line tool kubectl is required to run commands against Kubernetes clusters                                                                                                                    |
| [helm 3](https://github.com/helm/helm#install)                     | Helm Charts are used to package Kubernetes resources for each component |
| [argocd cli](https://argo-cd.readthedocs.io/en/stable/cli_installation)                     | ArgoCD CLI is required to manage the CHORUS-TRE ArgoCD instance |
| [argo cli](https://argo-workflows.readthedocs.io/en/stable/walk-through/argo-cli/)                            | Argo-Workflows CLI is required to manage CI jobs |

### Infrastructure
| Component          | Description                                                                                                        | Required |
| ------------------ | ------------------------------------------------------------------------------------------------------------------ | -------- |
| Kubernetes cluster | An infrastructure with a working Kubernetes cluster. | Required |
| Domain name        | CHORUS-TRE is only accessible via HTTPS and it's essential to register a domain name via registrars like Cloudflare, Route53, etc. | Required |  
| DNS Server         | CHORUS-TRE is only accessible via HTTPS and it's essential to have a DNS server via providers like Cloudflare, Route53, etc.                  | Required |
## Installation
### Bootstrap

1. Make sure your `KUBECONFIG` environment variable points to a Kubernetes cluster context, where the `build` environment of CHORUS will be installed.
2. Clone the `chorus-tre` repository:
   ```bash
   git clone git@github.com:CHORUS-TRE/chorus-tre.git
   ```
3. Modify the chorus ApplicationSet template for your use case:
   ```bash
   cd chorus-tre
   mv deployment/applicationset/applicationset-chorus.template.yaml deployment/applicationset/applicationset-chorus.yaml
   ```
   In this file, change the links to `https://github.com/<YOUR-ORG>/environments-template` to your new fork.
   
4. Execute the bootstrapping script and, when asked, the domain name you wish to deploy your instance to:
   ```bash
   ./bootstrap.sh
   Please enter domain name of your CHORUS instance: <domain_name>
   ```
This will bootstrap the installation of ArgoCD as well as the OCI registry to the specified domain name.

5. Login to ArgoCD with the username/password received during the previous step, and add the build cluster:
   ```bash
   argocd login <argo-cd URL>
   argocd cluster add <k8s-context> --in-cluster --label env=build --name=chorus-build
   ```
6. Fork the [environments-template](https://github.com/CHORUS-TRE/environments-template) repository to your GitHub organization.
   
### Secrets

### Deploy
