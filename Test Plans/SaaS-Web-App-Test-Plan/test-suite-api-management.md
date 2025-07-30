# Test Cases – Client Credentials & API Key Management

## Section 1: Creating a New API Key

| Test Case ID | Description                                                                 | Expected Result                         | Status                 |
|--------------|-----------------------------------------------------------------------------|-----------------------------------------|------------------------|
| TC_API_001   | Navigation to API Keys section from User Management tab is possible         | Section is reachable                    | PASS ✅|
| TC_API_002   | Clicking '+ Client Credentials' opens the detail panel                      | Detail panel appears                    | PASS ✅|
| TC_API_003   | 'Name' and 'Roles' fields are required                                      | Required validation enforced            | PASS ✅|
| TC_API_004   | Multiple roles can be selected and saved correctly                          | All selected roles saved accurately     | PASS ✅|
| TC_API_005   | Attempting to leave without saving triggers warning or confirmation         | Confirmation prompt shown               | PASS ✅|

## Section 2: Accessing the Client Secret

| Test Case ID | Description                                                                 | Expected Result                         | Status                 |
|--------------|-----------------------------------------------------------------------------|-----------------------------------------|------------------------|
| TC_API_006   | Client ID and secret are generated upon API key creation                    | Both are generated successfully         | PASS ✅|
| TC_API_007   | Client secret is only shown once                                            | Secret hidden after first view          | PASS ✅|
| TC_API_008   | Leaving without storing prompts confirmation dialog                         | Dialog appears as expected              | PASS ✅|
| TC_API_009   | 'Done' button inactive if checkbox unchecked                                | Button disabled                         | PASS ✅|
| TC_API_010   | Checkbox must be checked to proceed; secret hidden after                    | Secret hidden; 'DELETE API KEY' appears | PASS ✅|

## Section 3: Viewing API Keys

| Test Case ID | Description                                                                 | Expected Result                         | Status                 |
|--------------|-----------------------------------------------------------------------------|-----------------------------------------|------------------------|
| TC_API_011   | API keys displayed in table with Name, Roles, Client ID                     | Table shows all expected fields         | PASS ✅|
| TC_API_012   | Message displays number of credentials used                                 | Message accurate (e.g. “3 of 10”)       | PASS ✅|
| TC_API_013   | '+ API KEY' disabled when limit reached; tooltip explains                   | Limit respected and explained           | PASS ✅|
| TC_API_014   | Clicking a row opens detail view on right panel                             | Detail view opens                       | PASS ✅|

## Section 4: Editing an API Key

| Test Case ID | Description                                                                 | Expected Result                         | Status                 |
|--------------|-----------------------------------------------------------------------------|-----------------------------------------|------------------------|
| TC_API_015   | Pencil icon allows editing                                                  | Editing mode enabled                    | PASS ✅|
| TC_API_016   | Only 'Name' and 'Roles' editable                                            | Fields behave as expected               | PASS ✅|
| TC_API_017   | '+ Client Credentials' button remains disabled during edit                  | Button disabled during edit             | PASS ✅|

## Section 5: Deleting an API Key

| Test Case ID | Description                                                                 | Expected Result                         | Status                  |
|--------------|-----------------------------------------------------------------------------|-----------------------------------------|-------------------------|
| TC_API_018   | API key deletion from detail view                                           | Deletion successful                     | FAIL ❌, ⚠️ [Issue #734116](https://github.com/jeffery7jumman/QA---Portfolio/blob/main/bug-report/bug-report-api-deletion.md) |
| TC_API_019   | Confirmation dialog appears before deletion                                 | Dialog shown                            | BLOCKED ⛔|
| TC_API_020   | Deleted key is removed from list and inaccessible                           | Key removed                             | FAIL ❌, ⚠️ [Issue #734116](https://github.com/jeffery7jumman/QA---Portfolio/blob/main/bug-report/bug-report-api-deletion.md) |


## 📝 Outcome Summary

- Majority of test cases passed as expected.
- Critical issue found during deletion of API keys (Issue #734116).
- Feature is mostly stable, with proper validation, role handling, and secret visibility flows.
- Recommended follow-up: resolve deletion bug and retest that scenario after fix.
