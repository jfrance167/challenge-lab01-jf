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
