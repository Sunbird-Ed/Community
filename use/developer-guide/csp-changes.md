---
description: >-
  In release-6.0.0 SunbirdED is going with cloud agnostic. To achieve this
  SunbirdED has built the SDK to help all the service use same code base as much
  as it can.
---

# CSP changes

1. SunbirdED team has created a node SDK that will be used by all the node services for implementing the cloud agnostic features. for more details please refer the below link [https://github.com/Sunbird-Ed/client-cloud-services](https://github.com/Sunbird-Ed/client-cloud-services)
2. SunbirdED Team has created a SDK in scala which is used by all the backend services to implement the cloud service features. for more details refer link [https://github.com/project-sunbird/sunbird-cloud-storage-sdk](https://github.com/project-sunbird/sunbird-cloud-storage-sdk)
3. Sunbird editors has created the fileupload plugin for azure cloud service please refer the details here. [https://knowlg.sunbird.org/use/release-notes/release-5.5.0#file-upload-library](https://knowlg.sunbird.org/use/release-notes/release-5.5.0#file-upload-library)

SunbirdED has been tested in Azure Cloud provider and the application is working as expected.

CSP Implementation table

Node SDK ([client-cloud-services](https://github.com/Sunbird-Ed/client-cloud-services))

<table><thead><tr><th>Cloud Provider</th><th width="174.33333333333331">Implemented</th><th>Tested</th></tr></thead><tbody><tr><td>Azure</td><td>Yes</td><td>Yes</td></tr><tr><td>AWS</td><td>Yes</td><td>No</td></tr><tr><td>GCP</td><td>Yes</td><td>No</td></tr><tr><td>OCI</td><td>Yes</td><td>No</td></tr></tbody></table>

&#x20;Java SDK ([sunbird-cloud-storage-sdk](https://github.com/project-sunbird/sunbird-cloud-storage-sdk))

<table><thead><tr><th>Cloud Provider</th><th width="174.33333333333331">Implemented</th><th>Tested</th></tr></thead><tbody><tr><td>Azure</td><td>Yes</td><td>Yes</td></tr><tr><td>AWS</td><td>Yes</td><td>No</td></tr><tr><td>GCP</td><td>Yes</td><td>No</td></tr><tr><td>OCI</td><td>Yes</td><td>No</td></tr></tbody></table>

Editor Plugin([sunbird-file-upload-library](https://github.com/Sunbird-Knowlg/sunbird-file-upload-library/tree/main))

<table><thead><tr><th>Cloud Provider</th><th width="174.33333333333331">Implemented</th><th>Tested</th></tr></thead><tbody><tr><td>Azure</td><td>Yes</td><td>Yes</td></tr><tr><td>AWS</td><td>No</td><td>No</td></tr><tr><td>GCP</td><td>No</td><td>No</td></tr><tr><td>OCI</td><td>No</td><td>No</td></tr></tbody></table>
