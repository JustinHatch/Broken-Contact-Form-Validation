# Contact-form test cases

## Historical submission checks

These existing cases record the earlier submission/confirmation investigation. The failed and passed submission results are shown in the existing TestRail screenshots. They are retained as historical records, not results from a new execution of the restored validation demo. No original project or screenshot dates have been changed.

The restored HTML demo demonstrates email validation and simulated confirmation. It is not the same submission failure scenario described in CFV-001. Browser-native validation messages can appear beside the focused field rather than beside every field at once.

| Test Case ID | Test Scenario                        | Steps to Reproduce                                                                 | Expected Result                                               | Actual Result         | Status |
|--------------|--------------------------------------|-------------------------------------------------------------------------------------|----------------------------------------------------------------|------------------------|--------|
| CFV-001      | Submit form with all valid fields    | 1. Navigate to Contact Page → 2. Fill all fields → 3. Click Submit                  | Success message appears or redirect to thank-you page         | No response (pre-fix)  | ❌ Fail |
| CFV-002      | Submit form after bug fix            | Repeat CFV-001 steps after fix is implemented                                       | Success message shown / redirect triggered                    | Success confirmed      | ✅ Pass |
| CFV-003      | Submit with empty fields             | 1. Leave fields blank → 2. Click Submit                                             | Error messages should appear near each required field         | Errors show as expected| ✅ Pass |
| CFV-004      | Invalid email format                 | 1. Enter invalid email (e.g., “abc”) → 2. Click Submit                              | Email format validation error shown                           | Error displayed        | ✅ Pass |
| CFV-005      | JS console errors during submission  | 1. Open dev tools → 2. Submit form                                                  | No red console errors related to form submission              | No errors              | ✅ Pass |
| CFV-006      | Inspect POST network call            | 1. Open Network tab → 2. Submit form                                                | Proper POST request visible with correct form data            | Delivery not demonstrated by the published demo | Not verified |


CFV-006 previously claimed a successful POST. That claim is not supported by the published HTML: the submit handler calls `preventDefault()` and displays a local message. It is now marked **Not verified**; a confirmation message is not evidence of delivery.

## Recheck the existing validation demo

Use `QA Example` for the name and `Validation check` for the message. These steps are a verification guide, not additional historical pass results.

| Version | Input/action | Expected behavior |
| --- | --- | --- |
| Broken | Fill name and message, enter `abc` as email, click Send Message | Invalid email is accepted and the local demonstration message appears. |
| Broken | Fill name and message, leave email empty, click Send Message | Empty email is accepted; name and message still have required-field validation. |
| Fixed | Fill name and message, enter `abc` as email, click Send Message | Native email validation blocks submission. |
| Fixed | Leave any required field empty and click Send Message | Native required-field validation blocks submission. |
| Fixed | Fill name/message and email `qa@example.com`, click Send Message | Local success message appears and fields reset; no message is delivered to a backend. |
