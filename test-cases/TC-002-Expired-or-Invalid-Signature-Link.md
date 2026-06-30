# 📄 TC-002 - Expired or Invalid Signature Link

### 🎯 Objective
Verify that the system correctly handles expired or invalid signature links, preventing unauthorized access to the document.

---

### 📋 Preconditions
- [ ] A document has been sent for signature.
- [ ] The signature link has expired OR is invalid OR has been tampered with.
- [ ] The user attempts to access the document via email link.

---

### 🛣️ Test Steps

| Step | Action | Expected Result |
| :---: | :--- | :--- |
| 1 | Open the expired or invalid signature link. | The system detects the invalid request. |
| 2 | Attempt to access the document. | Access is denied. |
| 3 | System displays an error message. | A clear message is shown indicating the link is invalid or expired. |
| 4 | Attempt to refresh or reuse the link. | Access remains blocked. |

---

### 🚀 Expected Results
* **Access Control:** User cannot access the document via invalid/expired link.
* **User Feedback:** System displays a clear and user-friendly error message.
* **Data Protection:** No document data is exposed.
* **Compliance:** Security rules are enforced correctly.
* **Logs:** Access attempts are logged (if audit is enabled).

---

### 🛠️ Test Type
- Functional Testing
- Security Validation
- Negative Testing

---

### 🚨 Classification
* **Priority:** High
* **Severity:** High
