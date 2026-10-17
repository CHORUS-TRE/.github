# CHORUS

A secure processing environment for health data research at scale.

CHORUS brings researchers and their tools to sensitive data. Each project works in its own isolated workspace, and nothing enters or leaves without approval.

CHORUS is developed at the [Lausanne University Hospital (CHUV)](https://www.chuv.ch/en/) by the [Biomedical Data Science Center (BDSC)](https://www.chuv.ch/en/bdsc/), the [Information Systems Department (DSI)](https://www.chuv.ch/fr/fiches/direction-des-systemes-dinformation) and the [NeuroDigital](https://www.chuv.ch/fr/neurosciences/dnc-home/recherche/centre-de-recherche-en-neurosciences/neurotech/research-labs/neurodigitalneurotech) team of the [Department of Clinical Neurosciences (DNC)](https://www.chuv.ch/fr/neurosciences/dnc-home).

Website: [chorus-tre.ch](https://chorus-tre.ch)

## How it works

1. *Workspace* — each project gets its own secure workspace.
2. *Import* — data enters only once access is approved.
3. *Analysis* — researchers work with their usual tools, and the data never leaves the workspace.
4. *Export* — results leave only once they are reviewed and approved.

## What every workspace comes with

- Open, allow-listed or air-gapped network, set per workspace
- Browser sessions: data never reaches the researcher's laptop
- An App Store of more than 50 research apps, including JupyterLab, RStudio and VS Code
- PostgreSQL, MLflow, Gitea and more as workspace services
- Approval workflow for data entering and leaving a workspace
- Role-based access control and audit trail
- Single sign-on with your institution's identity provider

CHORUS installs on any Kubernetes cluster with Cilium as the network layer: in your data centre, in a private or public cloud, or on an isolated site with no internet access. It also needs S3-compatible object storage and a domain name you control. [See the requirements](https://chorus-tre.ch/pricing-deployment/)

## Compliance

CHORUS is designed around the Five Safes, and designed to align with the European Health Data Space (EHDS) and TEHDAS2, SATRE v2 and the General Data Protection Regulation (GDPR). [Read more](https://chorus-tre.ch/compliance/)

## Editions

- *Community Edition* — the complete platform, free for academic non-commercial research, self-hosted. Available now.
- *Pro Edition* — Pro features on top of the Community Edition, self-hosted. In development.
- *Managed* — hosted and operated by the CHORUS team. In development.

[Compare editions](https://chorus-tre.ch/pricing-deployment/)

## Get started

- [Get the Community Edition](https://chorus-tre.ch/contact-us/?topic=community-edition), free for academic non-commercial research
- [Documentation](https://docs.chorus-tre.ch/) for researchers, data managers and platform administrators
- [Join the community](https://chorus-tre.ch/community/) to get the Community Edition and its code, contribute to CHORUS and give feedback to the team
- [Request a demo](https://chorus-tre.ch/contact-us/?topic=demo)
- [Contact us](https://chorus-tre.ch/contact-us/)

## License and Usage Restrictions

CHORUS is licensed for academic non-commercial research only, under the terms of the [license agreement](https://github.com/CHORUS-TRE/.github/blob/master/LICENSE).

Any use of the software for purposes other than academic research, including for commercial purposes, shall be requested in advance from [CHUV](https://chorus-tre.ch/contact-us/?topic=licensing).
