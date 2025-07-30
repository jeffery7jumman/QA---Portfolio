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

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_001    | Launch the app and tap ‘Join’                                               | Navigates to account creation screen                  | ✅     |
| TC_CARD_002    | Enter valid first and last name (letters only)                              | Name is accepted                                      | ✅     |
| TC_CARD_003    | Enter invalid characters in name (e.g. numbers, emoji)                      | Validation error shown                                | ✅     |
| TC_CARD_004    | Enter valid email format                                                    | Email accepted                                        | ✅     |
| TC_CARD_005    | Enter invalid email                                                         | Validation error shown                                | ✅     |
| TC_CARD_006    | Enter secure password (min 10 chars, upper/lower/numbers/symbols)           | Password accepted                                     | ✅     |
| TC_CARD_007    | Enter weak password (e.g. "password123")                                    | Validation error shown                                | ✅     |

---

## 2. Phone Number & SMS Preferences

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_008    | Enter valid phone number                                                    | Number accepted                                       | ✅     |
| TC_CARD_009    | Enter alphabetic or short phone number                                      | Validation error shown                                | ✅     |
| TC_CARD_010    | Toggle SMS promotional preference                                           | Toggle functions and is saved                         | ✅     |

---

## 3. Phone Number Verification

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_011    | Enter incorrect/expired code                                                | Error shown                                        | ✅     |
| TC_CARD_012    | Request code again                                                          | Code is re-sent and accepted                          | ✅     |
| TC_CARD_013    | Enter valid verification code                                               | Phone verified                                           | ✅     |


---

## 4. Address Input

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_014    | Leave address fields blank                                                  | Required field error shown                            | ✅     |
| TC_CARD_015    | Enter invalid postal code or state                                          | Suggestion or error shown                             | ✅     |
| TC_CARD_016    | Enter complete, valid address                                               | Address accepted                                      | ✅     |

---

## 5. DOB & SSN Entry

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_017    | Leave DOB/SSN blank                                                         | Required field error shown                            | ✅     |
| TC_CARD_018    | Enter invalid format for DOB/SSN                                            | Validation error shown                                | ✅     |
| TC_CARD_019    | Enter valid DOB and SSN                                                     | Info accepted                                         | ✅     |


---

## 6. Info Validation & Biometrics

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_020    | Edit fields in validation step (name, address, phone)                       | Fields editable and updated                           | ✅     |
| TC_CARD_021    | Enable or decline biometric login                                           | Selection is saved                                    | ✅     |


---

## 7. Product & Credit Amount Selection

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_022    | Select ‘Build Credit with Card’ option                                      | SCC option selectable                                 | ✅     |
| TC_CARD_023    | Enter invalid custom credit amount                                          | Validation error shown                                | ✅     |
| TC_CARD_024    | Choose valid credit amount option                                           | Amount accepted                                       | ✅     |


---

## 8. Repayment Date

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_025    | Try adding invalid date (e.g. 0 or 32)                                      | Validation error shown                                | ✅     |
| TC_CARD_026    | Add a valid repayment date (1-30)                                           | Date accepted                                         | ✅     |


---

## 9. Bank Account Linking

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_027    | Attempt to proceed without linking funding source                           | App blocks progression                                | ✅     |
| TC_CARD_028    | Link bank account using Plaid                                               | Plaid link works and info retrieved                   | ✅     |
| TC_CARD_029    | Enter bank account manually                                                 | Manual info accepted                                  | ✅     |
| TC_CARD_030    | Add an invalid debit card as a payment method                               | Card declined                                         | ✅     |
| TC_CARD_031    | Add a valid debit card as a payment method                                  | Card accepted

---

## 10. Final Confirmation

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_032    | Edit repayment method or date before confirming                             | Edits allowed                                         | ✅     |
| TC_CARD_033    | Attempt completing onboarding without accepting repayment terms             | Error displayed and affected field is higlited in Red |
| TC_CARD_034    | Accept repayment terms and continue                                         | Onboarding completes with success modal               | ✅     |
| TC_CARD_035    | Close Success modal using X button                                          | Modal closed, and dashboard is displayed              |

---

## 11. SCC Setup on Dashboard (Web Flow)

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_036    | Tap ‘Set up SCC’ button from dashboard                                      | Navigates to web setup page                           | ✅     |
| TC_CARD_037    | Validate Income and Expenses form                                           | Values required and validated                         | ✅     |
| TC_CARD_038    | Use credit slider                                                           | Slider works and updates limit field                  | ✅     |
| TC_CARD_039    | Skip funding source on web                                                  | App blocks progression                                | ✅     |
| TC_CARD_040     | Select payment method added during onboarding                               | Added as a funding source                             |
| TC_CARD_041     | Add a new funding source using Plaid, manually or debit card                | New source added as a funding source                  |
| TC_CARD_042    | Add delivery address                                                        | Address required and validated                        | ✅     |
| TC_CARD_041    | Accept terms and complete setup                                             | Setup finishes and success page shown                 | ✅     |

---

## 12. Card Activation & Login

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_039    | View SCC card on dashboard after setup                                      | Card appears with ‘Activate’ button                   | ✅     |
| TC_CARD_040    | Try activating card without CVV                                             | App blocks activation with message                    | ✅     |
| TC_CARD_041    | Reopen app and use biometrics (if enabled)                                 | Biometric login prompt shown                          | ✅     |
| TC_CARD_042    | Reopen app without biometrics                                               | Email + password required                             | ✅     |
