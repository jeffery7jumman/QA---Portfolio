# Test Cases – Reporting Group (RG) Announcement & Configuration

## Description

This document includes test cases for managing Reporting Groups (RGs), particularly features related to rounding unit confirmation, quota configurations, announcement handling, inheritance, and restricted editing behaviors.

These test cases validate:
- UI visibility and interaction flows
- Confirmation dialogs and edit logic
- Announcement ID management across different input scenarios
- Parent-child RG inheritance behavior
- Restricted editing from specific UI entry points

---

## Confirm Rounding Unit

| Test Case ID | Description                                                                 | Expected Result                                       | Status           |
|--------------|-----------------------------------------------------------------------------|-------------------------------------------------------|------------------|
| TC_RG_021    | Navigate to RG detail page; check if "Confirm Rounding Unit" is visible without edit mode | Button is visible                       | PASS             |
| TC_RG_022    | Click "Confirm Rounding Unit"; dialog should be clear; confirm and attempt edit | Confirmation registered, edit restricted          | PASS             |
| TC_RG_023    | Revoke confirmation, change value, confirm again with new value             | Value updates correctly                               | PASS             |

---

## Edit Quota Section

| Test Case ID | Description                                                                 | Expected Result                                       | Status           |
|--------------|-----------------------------------------------------------------------------|-------------------------------------------------------|------------------|
| TC_RG_024    | Navigate to Quota section; test valid, invalid, and boundary values         | Validations enforce correct input                     | PASS             |
| TC_RG_025    | Confirm no regression from recent changes                                   | All expected behaviors remain                         | ⚠️ Issue #737983 |

---

## Edit Announcement Handling Section

| Test Case ID | Description                                                                 | Expected Result                                       | Status           |
|--------------|-----------------------------------------------------------------------------|-------------------------------------------------------|------------------|
| TC_RG_026    | Add announcement IDs across all three cases; verify display                 | Display accurate for each case                        | PASS             |
| TC_RG_027    | Leave all fields empty; check for fallback message                          | “No announcement behavior configured” message appears | PASS             |
| TC_RG_028    | Add ID to any field and check for green checkmark                           | Checkmark appears in column                           | PASS             |
| TC_RG_029    | Mix filled and empty fields; validate handling logic                        | System processes inputs correctly                     | PASS             |

---

## Child RGs and Inheritance

| Test Case ID | Description                                                                 | Expected Result                                       | Status           |
|--------------|-----------------------------------------------------------------------------|-------------------------------------------------------|------------------|
| TC_RG_030    | Navigate to child RG; check for inheritance note                            | Note is visible                                       | PASS             |
| TC_RG_031    | Confirm child RG inherits announcement behavior when unset locally          | Inheritance applies correctly                         | PASS             |
| TC_RG_032    | Create parent-child pair; test inheritance logic                            | Expected settings inherited                           | PASS             |
| TC_RG_033    | Modify parent settings; observe effects on child                            | Child updates as expected                             | PASS             |

---

## Action Menus and RG Editing Access

| Test Case ID | Description                                                                 | Expected Result                                        | Status           |
|--------------|-----------------------------------------------------------------------------|--------------------------------------------------------|------------------|
| TC_RG_034    | Open RG list; verify "Edit" action is removed from menu                     | "Edit" option is not visible                           | PASS             |
| TC_RG_035    | Confirm editing is only accessible via right panel                          | Access allowed only through detail view                | PASS             |

---

## 📝 Outcome Summary

- All key configurations and confirmation workflows behave as expected.
- Minor regression detected in the Quota section (Issue #737983).
- Inheritance and UI limitations were properly enforced.
- Recommendation: Resolve quota validation bug and retest under edge cases.

