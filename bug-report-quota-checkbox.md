# Bug Report – Quota Checkbox State Reversion

## Bug ID: #737983  
**Category**: [Chrome][Quota]  
**Title**: Checkbox state reverts visually after saving changes in 'Dynamic Quota' settings despite backend update

---

### Feature
Network > Rating Group > Voice > Quota

### Test Run
#2905  
Date: 20/07/2025–21/07/2025
Severity: Medium  
Reproducibility: ✅ 3/3

### 🌐 Environment
- **Device**: MacBook Pro (15-inch, 2019)  
- **OS**: macOS Sequoia 15.5  
- **Browser**: Chrome  
- **App Version**: https://xxxxxxxxxxxx.xxxx  
- **Network**: Wi-Fi  
- **Location**: Kenya  

---

### 🔁 Steps to Reproduce

0. Ensure another 'Network' category tab is open in the same browser window  
1. Log in to the system  
2. Navigate to **Network** > **Reporting Group** > **Voice**  
3. Click the **edit** icon for the **Quota** section  
4. Toggle the **Dynamic Quota** checkbox (check or uncheck)  
5. Click **Save**  
6. Observe the checkbox state after save

---

### Expected Result
The UI should immediately reflect the updated state of the 'Dynamic Quota' checkbox (checked or unchecked), accurately matching the user’s selection.

---

### Actual Result
The checkbox visually reverts to its previous state after clicking **Save**, even though the backend correctly records the update. The correct state is only visible after:
- Refreshing the page, or  
- Reopening the section

---

### Notes & Impact

- Affects users multitasking across multiple tabs within the **Network** category — a common behavior for admins and power users.
- May lead to confusion and repeated toggling actions, resulting in potential data inconsistencies or redundant updates.
- UI desync with backend state may affect trust in the system’s responsiveness.

---

### Suggested Fix

Ensure UI components properly rebind to the updated state from the backend after save action completes, especially in multi-tab scenarios.

