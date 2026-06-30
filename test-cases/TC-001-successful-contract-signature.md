# 📄 TC-001 - Successful Document Signature (Autentique-like Flow)

### 🎯 Objective
Verify that a document can be successfully signed through the electronic signature workflow, ensuring all signers complete the process and the system correctly updates the document status.

---

### 📋 Preconditions
- [ ] A document has been uploaded to the platform.
- [ ] The document has been sent for signature to one or more signers.
- [ ] All signers have received the email invitation link.
- [ ] The document status is **Waiting for signatures**.
- [ ] The signature request is active and not expired.

---

### 🛣️ Test Steps

| Step | Action | Expected Result |
| :---: | :--- | :--- |
| **1** | Open the signature invitation link received by email. | The document signing page is displayed successfully. |
| **2** | Authenticate the signer (if required). | User is validated and gains access to the document. |
| **3** | Review the document content. | Document is displayed correctly and fully accessible. |
| **4** | Click on the signature field. | Signature area is activated. |
| **5** | Confirm the signature. | Signature is successfully applied. |
| **6** | If multiple signers exist, repeat the process. | All required signatures are collected. |
| **7** | Access the final document. | Signed PDF is generated and available for download. |

---

### 🚀 Expected Results
* **Status Update:** Document status is updated to *Fully signed*.
* **File Generation:** Final signed PDF is generated.
* **Security:** Audit trail is created with timestamp and signer details.
* **Communication:** Notification emails are sent to all participants.
* **Logs:** Signature history is stored in the system.
* **Integrity:** Document becomes immutable after completion.

---

### 🛠️ Test Type
- Functional Testing
- End-to-End Testing
- Regression Testing
- API Validation *(if applicable)*
- Audit Trail Validation

---

### 🚨 Classification
* **Priority:** 🔴 High
* **Severity:** ⚡ Critical
