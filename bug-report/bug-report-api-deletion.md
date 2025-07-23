# Bug Report – Client Credentials Deletion Failure

## Bug ID: #734116  
**Category**: [Chrome][User Management][Client Credentials]  
**Title**: 'Internal Error' displayed when deleting client credentials

---

### Feature
User Management > Client Credentials

### Test Run
#2818  
Date: 06/07/2025–07/07/2025

Severity: High  
Reproducibility: ✅ 3/3

### 🌐 Environment
- **Device**: MacBook Pro (15-inch, 2019)  
- **OS**: macOS Sequoia 15.5  
- **Browser**: Chrome  
- **App Version**: [https://XXXXXXXXXXX.XXXXXX](https://xxxxxxxxxxxxxxxxxxx.xxx)  
- **Network**: Wi-Fi  
- **Location**: Kenya  

---

### 🔁 Steps to Reproduce

1. Navigate to the **User Management** section  
2. Open the **Client Credentials** tab  
3. Select an existing client credential  
4. Attempt to delete the selected credential

---

### Expected Result
The selected client credential should be successfully deleted, the total count should be updated, and the interface should allow the creation of a new credential if under the limit.

---

### Actual Result
An error message appears:  **'The operation could not be completed due to an internal error'**.  
The credential remains undeleted.

---

### Notes & Impact

- Blocks users from managing their client credentials effectively.
- Prevents deletion even if within the credential limit (e.g., 10 max), affecting API key rotation and cleanup processes.
- No recovery or retry mechanism shown in the UI after the error.

---

### Suggested Fix

- Investigate backend exception thrown during the deletion request.
- Improve error messaging for clarity (e.g., 'Credential is in use', 'Permission denied').
- Ensure client credentials are not linked to active services before deletion.
