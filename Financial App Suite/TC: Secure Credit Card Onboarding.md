# Test Cases – Secure Credit Card Onboarding Flow

## Description

This document includes test cases for onboarding a new user who selects the “Build Credit with Card” option within a financial application. Tests are conducted via BrowserStack and focus on UI behavior, validation logic, restricted activation behavior, and biometric re-entry after onboarding.

These test cases validate:
- Proper visibility and flow of the onboarding process
- Handling of invalid and edge-case financial inputs during card set-up
- Enforcement of funding source requirements when setting up the card
- Visibility and restrictions around card activation
- Biometric login functionality after onboarding

---

## Onboarding UI & Flow

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_001    | Launch the app and start onboarding                                         | Onboarding screen is shown                           | ✅     |
| TC_CARD_002    | Select “Build Credit with Card” option                                      | Option is visible and selectable                      | ✅     |
| TC_CARD_003    | Try to exit the onboarding midway                                           | App prompts confirmation or blocks exit               | ✅     |

---

## Financial Input Validations

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_004    | Enter realistic income, expenses, credit limit                              | App accepts values without error                      | ✅     |
| TC_CARD_005    | Enter negative income or expense values                                     | App rejects with appropriate error                    | ✅     |
| TC_CARD_006    | Enter exaggerated values (e.g., millions) for income, expenses, credit limit| App flags values as invalid or out of range           | ✅     |

---

## Funding Source Validations

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_007    | Leave funding source blank                                                  | Error shown; field is required                        | ✅     |
| TC_CARD_008    | Enter funding source that cannot cover expenses                            | App blocks with validation error                      | ✅     |

---

## Card Activation Behavior

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_009    | Complete onboarding and proceed to Secure Card setup                        | “Activate My Card” field becomes visible              | ✅     |
| TC_CARD_010    | Attempt to activate card without physical card or number                    | Activation fails; proper message shown                | ✅     |

---

## Biometric Re-login

| Test Case ID   | Description                                                                 | Expected Result                                       | Status |
|----------------|-----------------------------------------------------------------------------|-------------------------------------------------------|--------|
| TC_CARD_011    | Close and reopen app; attempt biometric login                               | Biometric login prompt appears and works as expected  | ✅     |

---

## 📝 Outcome Summary

- All onboarding steps are functional and properly validated.
- Invalid values are handled with appropriate messaging.
- Card activation is blocked unless correct card info is available.
- Biometrics work after onboarding, improving user experience.
- No real user data used—test accounts are anonymized.
