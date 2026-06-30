# 📄 TC-003 - Partial Signature in a Multi-Signer Workflow

### 🎯 Objective
Verify that the system correctly handles a document with multiple signers when only part of the required signatures have been completed.

---

### 📋 Preconditions
- [ ] A document has been uploaded to the platform.
- [ ] The document requires signatures from multiple signers.
- [ ] Signature requests have been sent to all signers.
- [ ] The document status is **Waiting for signatures**.
- [ ] At least one signer has not yet signed the document.

---

### 🛣️ Test Steps

| Step | Action | Expected Result |
| :---: | :--- | :--- |
| **1** | Sign the document using the first signer's invitation link. | The signature is successfully applied. |
| **2** | Access the document details. | The document reflects the completed signature. |
| **3** | Verify the status of the document. | The document remains in a pending state awaiting remaining signatures. |
| **4** | Check the signature history. | The completed signature is recorded. |
| **5** | Verify pending signers. | Remaining signers are identified as pending. |
| **6** | Access the document as a pending signer. | The signer can still review and sign the document. |

---

### 🚀 Expected Results
* **Progress Tracking:** The completed signature is recorded successfully.
* **Status Continuity:** The document status remains *Partially Signed* or *Waiting for Remaining Signatures*.
* **Validation:** The document is not marked as fully signed.
* **File Integrity:** The final signed PDF is not generated until all required signatures are completed.
* **Security:** Audit records contain information about completed and pending signatures.
* **Workflow:** Remaining signers can continue the signing process normally.

---

### 🛠️ Test Type
- Functional Testing
- End-to-End Testing
- Workflow Validation
- Audit Trail Validation

---

### 🚨 Classification
* **Priority:** High
* **Severity:** High
