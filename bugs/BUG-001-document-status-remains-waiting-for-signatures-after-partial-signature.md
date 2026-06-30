# 🐞 BUG-001 - Document Status Remains "Waiting for Signatures" After Partial Signature

## Work Item Information

| Field | Value |
|------|------|
| **Work Item Type** | Bug |
| **ID** | BUG-001 |
| **Title** | Document status remains "Waiting for Signatures" after the first signer completes the signature |
| **Area Path** | Contract Management\Electronic Signature |
| **Iteration Path** | Sprint 12 |
| **State** | Active |
| **Reason** | New |
| **Assigned To** | Development Team |
| **Reported By** | QA Team |
| **Priority** | 2 |
| **Severity** | High |
| **Tags** | Electronic Signature; Workflow; Status Update; Regression |

## Description

After the first signer successfully completes the signing process, the document status is not updated accordingly. Instead of reflecting that one required signature has been completed, the system continues displaying **Waiting for Signatures**.

This issue occurs in documents requiring multiple signers and may cause users to believe that no progress has been made in the signing workflow.

## Environment

| Property | Value |
|----------|-------|
| **Environment** | QA |
| **Platform** | Web |
| **Browser** | Google Chrome (Latest Version) |
| **Operating System** | Windows 11 |
| **Application Version** | v1.12.0 |
| **API Version** | v1 |

## Preconditions

- A document requiring signatures from at least two signers has been created.
- Signature requests have been successfully sent to all signers.
- The document status is **Waiting for Signatures**.
- The first signer has access to a valid signing link.
- API endpoints are available for validation.
- Database records are accessible for verification.

  ## Steps to Reproduce

| Step | Action |
|------|--------|
| 1 | Open the first signer's invitation link. |
| 2 | Review the document information. |
| 3 | Complete the signing process. |
| 4 | Return to the document details page and verify the displayed status. |
| 5 | Send a request to retrieve the document information using Postman. |
| 6 | Execute an SQL query to verify the document status stored in the database. |
| 7 | Compare the information displayed in the UI, API response, and database records. |

## Expected Result

After the first signer completes the signing process:

- The document status is updated to **Partially Signed** (or the corresponding intermediate status).
- The UI displays the updated document status.
- The API returns the updated document status.
- The database stores the updated status correctly.
- The audit trail records the completed signature.
- Remaining signers can continue the signing process.

  ## Actual Result

After the first signer completes the signing process:

- The UI continues displaying **Waiting for Signatures**.
- The API returns the document with the outdated status.
- The database keeps the document status unchanged.
- The completed signature is recorded, but the document workflow is not updated accordingly.

  ## Business Impact

- Users may incorrectly assume that no signatures have been completed.
- Business users may delay the approval process due to the incorrect document status.
- Customer Support may receive unnecessary inquiries regarding the signing progress.
- Workflow tracking becomes unreliable, impacting operational efficiency.
- Incorrect status information may affect reports and business metrics.

  ## Investigation

The issue was investigated using the following tools and techniques:

- **Azure DevOps** to review the related Feature, Product Backlog Item (PBI), Test Task, and Bug.
- **Postman** to validate the API response and compare the document status returned by the backend.
- **SQL Server** to verify whether the document status and signature records were correctly persisted.
- **Browser Developer Tools** to inspect network requests and responses during the signing process.

The collected information indicated an inconsistency between the expected workflow behavior and the persisted document status.

## Reproducibility

**Always (5/5 attempts)**

The issue was consistently reproduced following the same steps across multiple test executions in the QA environment.

## Related Test Case

**TC-003 - Partial Signature in a Multi-Signer Workflow**

## Links

| Type | Reference |
|------|----------|
| PBI | PBI-024 - Electronic Signature Workflow |
| Test Case | TC-003 - Partial Signature in a Multi-Signer Workflow |
| Bug | BUG-001 |

## History

| Date | Action |
|------|--------|
| 2026-06-30 | Bug created and documented by QA |
| 2026-06-30 | Investigation completed using API and SQL validation |
| 2026-06-30 | Evidence documented and linked to test case |

