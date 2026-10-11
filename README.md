# Contact Form Validation — QA Practice

An existing manual QA project covering contact-form behavior, defect documentation, and fix verification with Jira and TestRail. The published HTML examples demonstrate a missing email-validation check and its correction.

## Demonstrated defect and fix

- **Broken version:** email uses `type="text"` without `required`, so invalid or empty email is accepted when name and message are filled. Name and message already have required-field checks.
- **Fixed version:** email uses `type="email"` and `required`. Browser-native validation blocks invalid or missing input; valid input displays a local confirmation and resets the form.
- **Scope:** front-end validation and simulated submission. Neither example sends a POST request or delivers a message to a site owner.

The HTML files were restored from my existing Wix examples, replacing gallery files that had been uploaded to this repository by mistake:

- [Existing broken form source](https://daboij1-wixsite-com.filesusr.com/html/44eba5_c5040dedde868553ecd14d31ee675363.html)
- [Existing fixed form source](https://daboij1-wixsite-com.filesusr.com/html/44eba5_2c441aa0752eb950627fb37eb15044f0.html)

Open each `index.html` in a browser and follow the [validation recheck steps](TestCases.md#recheck-the-existing-validation-demo).

## Existing QA evidence

- [Test cases and scope notes](TestCases.md)
- [TestRail case](screenshots/contact%20form%20broke%20file.png)
- [TestRail failed result and passed retest](screenshots/contact%20form%20broke%20file%20tests.png)
- [Jira backlog](screenshots/1%20before%20sprint%20start.png), [task flow](screenshots/2%20contact%20form%20broke%20jira%20fix.png), and [completion](screenshots/3%20finished.png)

The TestRail screenshots document an earlier no-response/confirmation submission issue. They remain unchanged historical evidence; they do not prove backend delivery by the restored demo. The unsupported POST result is identified in the test-case notes.

## Repository contents

```text
broken-version/index.html  # Existing email-validation defect demo
fixed-version/index.html   # Existing corrected validation demo
screenshots/               # Original Jira and TestRail evidence
TestCases.md               # Historical records and current demo scope
README.md
```

Skills demonstrated: manual functional testing, invalid-input checks, test-case documentation, defect tracking, and retesting. This is portfolio project experience, not a claim of professional QA employment.
