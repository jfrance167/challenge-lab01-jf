# Cloud Computing Architecture Challenge Lab 1

This repository preserves work from my **Cloud Computing Architecture** course. It documents an Azure storage challenge lab and is presented as coursework rather than a production deployment.

## What I worked on

- Exported an Azure Resource Manager template for a StorageV2 account and its storage services.
- Required HTTPS traffic and TLS 1.2.
- Disabled public blob access.
- Created private blob containers as part of the lab environment.
- Added a lifecycle-management rule that moves matching block blobs to the Cool tier after 30 days.

## Repository contents

- `student-submissions/jf/exported/template.json` - exported ARM deployment template.
- `student-submissions/jf/exported/policy.json` - exported lifecycle policy.
- `student-submissions/jf/exported/lifecycle-policy.json` - a second copy of the lifecycle policy retained from the submission workflow.

## Course context

These files reflect a hands-on learning exercise in Azure resource deployment, storage configuration, lifecycle management, and infrastructure-as-code review. Some naming and folder structure follow the original course submission format.

The templates are retained as evidence of the learning process. They should be reviewed and updated before reuse because cloud APIs, security guidance, and organizational requirements change over time.

## Local review and safe reuse

Clone this repository and inspect the Markdown and JSON files locally; no cloud
subscription or deployment is needed to review the coursework. These exports are
historical evidence. Empty parameter files and export placeholders, where noted
above, are not deployable templates and are deliberately preserved.

Use only an isolated subscription you own or are authorized to administer, with
a cost limit and teardown plan, for any future exercise. Review actual network
access, identities, credentials, names and API versions before deploying. Never
commit local credentials or production resource exports. See [SECURITY.md](SECURITY.md).

The retained storage export permits public-network access; private containers
still require authorization and this does not prove anonymous data access.
For a new deployment, evaluate the following storage-account properties together
with private endpoint/DNS configuration and Microsoft Entra role assignments:

```json
{
  "publicNetworkAccess": "Disabled",
  "allowSharedKeyAccess": false,
  "defaultToOAuthAuthentication": true,
  "allowBlobPublicAccess": false,
  "supportsHttpsTrafficOnly": true,
  "minimumTlsVersion": "TLS1_2"
}
```

This is a proposed hardening excerpt, not a complete deployment. Validate clients
and management access before applying it; disabling shared keys can break older
clients. The original course exports have not been rewritten or redeployed.

## Repository map

```text
challenge-lab01-jf/
|-- .gitignore
|-- README.md
|-- SECURITY.md
`-- student-submissions/
```

Follow the setup and safety boundaries above before running or deploying any code.
