# Test Suite – Secure Credit Card (SCC) Onboarding Flow

## Extended Description

This test suite validates the full onboarding experience for the Secure Credit Card (SCC) feature in a financial app. It covers:

- UI flow from account creation through to card activation
- Field validations for name, email, phone number, address, SSN, and DOB
- Business logic around credit setup and repayment date selection
- Funding source enforcement (bank linking or debit card)
- Card setup via web, including slider controls and address input
- Biometric login behavior post-onboarding

Tested across common scenarios, edge cases, and invalid input handling.

---

## 1. App Launch & Account Creation

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_001    | Launch the app and tap ‘Join’                                               | Navigates to account creation screen                  | PASS ✅     |
| TC_CARD_002    | Enter valid first and last name (letters only)                              | Name is accepted                                      | PASS ✅     |
| TC_CARD_003    | Enter invalid characters in name (e.g. numbers, emoji)                      | Validation error shown                                | PASS ✅     |
| TC_CARD_004    | Enter valid email format                                                    | Email accepted                                        | PASS ✅     |
| TC_CARD_005    | Enter invalid email                                                         | Validation error shown                                | PASS ✅     |
| TC_CARD_006    | Enter secure password (min 10 chars, upper/lower/numbers/symbols)           | Password accepted                                     | PASS ✅     |
| TC_CARD_007    | Enter weak password (e.g. "password123")                                    | Validation error shown                                | PASS ✅     |

---

## 2. Phone Number & SMS Preferences

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_008    | Enter valid phone number                                                    | Number accepted                                       | PASS ✅     |
| TC_CARD_009    | Enter alphabetic or short phone number                                      | Validation error shown                                | PASS ✅     |
| TC_CARD_010    | Toggle SMS promotional preference                                           | Toggle functions and is saved                         | PASS ✅     |

---

## 3. Phone Number Verification

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_011    | Enter incorrect/expired code                                                | Error shown                                           | PASS ✅     |
| TC_CARD_012    | Request code again                                                          | Code is re-sent and accepted                          | PASS ✅     |
| TC_CARD_013    | Enter valid verification code                                               | Phone verified                                        | PASS ✅     |


---

## 4. Address Input

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_014    | Leave address fields blank                                                  | Required field error shown                            | PASS ✅     |
| TC_CARD_015    | Enter invalid postal code or state                                          | Suggestion or error shown                             | PASS ✅     |
| TC_CARD_016    | Enter complete, valid address                                               | Address accepted                                      | PASS ✅     |

---

## 5. DOB & SSN Entry

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_017    | Leave DOB/SSN blank                                                         | Required field error shown                            | PASS ✅     |
| TC_CARD_018    | Enter invalid format for DOB/SSN                                            | Validation error shown                                | PASS ✅     |
| TC_CARD_019    | Enter valid DOB and SSN                                                     | Info accepted                                         | PASS ✅     |


---

## 6. Info Validation & Biometrics

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_020    | Edit fields in validation step (name, address, phone)                       | Fields editable and updated                           | PASS ✅     |
| TC_CARD_021    | Enable or decline biometric login                                           | Selection is saved                                    | PASS ✅     |


---

## 7. Product & Credit Amount Selection

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_022    | Select ‘Build Credit with Card’ option                                      | SCC option selectable                                 | PASS ✅     |
| TC_CARD_023    | Enter invalid custom credit amount                                          | Validation error shown                                | PASS ✅     |
| TC_CARD_024    | Choose valid credit amount option                                           | Amount accepted                                       | PASS ✅     |


---

## 8. Repayment Date

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_025    | Try adding invalid date (e.g. 0 or 32)                                      | Validation error shown                                | PASS ✅     |
| TC_CARD_026    | Add a valid repayment date (1-30)                                           | Date accepted                                         | PASS ✅     |


---

## 9. Bank Account Linking

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_027    | Attempt to proceed without linking funding source                           | App blocks progression                                | PASS ✅     |
| TC_CARD_028    | Link bank account using Plaid                                               | Plaid link works and info retrieved                   | PASS ✅     |
| TC_CARD_029    | Enter bank account manually                                                 | Manual info accepted                                  | PASS ✅     |
| TC_CARD_030    | Add an invalid debit card as a payment method                               | Card declined                                         | PASS ✅     |
| TC_CARD_031    | Add a valid debit card as a payment method                                  | Card accepted                                         | PASS ✅     |

---

## 10. Final Confirmation

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_032    | Edit repayment method or date before confirming                             | Edits allowed                                         | PASS ✅     |
| TC_CARD_033    | Attempt completing onboarding without accepting repayment terms             | Error displayed and affected field is higlited in Red | PASS ✅     |
| TC_CARD_034    | Accept repayment terms and continue                                         | Onboarding completes with success modal               | PASS ✅     |
| TC_CARD_035    | Close Success modal using X button                                          | Modal closed, and dashboard is displayed              | PASS ✅     |

---

## 11. SCC Setup on Dashboard (Web Flow)

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_036    | Tap ‘Set up SCC’ button from dashboard                                      | Navigates to web setup page                           | PASS ✅     |
| TC_CARD_037    | Validate Income and Expenses form                                           | Values required and validated                         | PASS ✅     |
| TC_CARD_038    | Use credit slider                                                           | Slider works and updates limit field                  | PASS ✅     |
| TC_CARD_039    | Skip funding source on web                                                  | App blocks progression                                | PASS ✅     |
| TC_CARD_040    | Select payment method added during onboarding                               | Added as a funding source                             | PASS ✅     |
| TC_CARD_041    | Add a new funding source using Plaid, manually or debit card                | New source added as a funding source                  | PASS ✅     |
| TC_CARD_042    | Add delivery address                                                        | Address required and validated                        | PASS ✅     |
| TC_CARD_043    | Leave Accept terms checkbox unchecked                                       | 'Complete Set-up' button remains disabled             | PASS ✅     |
| TC_CARD_044    | Accept terms and complete setup                                             | Setup finishes and success page shown                 | FAIL ❌, ⚠️ Issue [#734127](https://github.com/jeffery7jumman/QA---Portfolio/blob/main/bug-report/bug-report-scc-setup.md)     |

---

## 12. Card Activation & Login

| Test Case ID   | Description                                                                 | Expected Result                                       | Status      |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|-------------|
| TC_CARD_045    | View SCC card on dashboard after setup                                      | Card appears with ‘Activate’ button                   | BLOCKED ⛔  |
| TC_CARD_046    | Try activating card without CVV                                             | App blocks activation with message                    | BLOCKED ⛔  |
| TC_CARD_047    | Reopen app and use biometrics (if enabled)                                  | Biometric login prompt shown                          | PASS ✅     |
| TC_CARD_048    | Reopen app without biometrics                                               | Email + password required                             | PASS ✅     |

---

## ✅ Summary

This test suite validates 48 test cases covering the full Secure Credit Card (SCC) onboarding journey, from app launch to card activation and login. It ensures:

- UI visibility and flow are intuitive and correctly sequenced
- Field-level validations prevent incorrect data entry
- Funding source enforcement and product logic are applied consistently
- Users cannot bypass key compliance steps like identity verification or linking a bank
- Biometric login and post-setup behaviors function as expected

- ✅ 45 test cases passed successfully with expected behavior
- ❌ 1 test case (**TC_CARD_044**) failed due to a known issue [#734127], where card setup does not complete as expected
- ⛔ 2 test cases (**TC_CARD_045** and **TC_CARD_046**) are currently blocked as a result of this failure

No additional critical issues were identified. Further regression is pending resolution of the blocker.
