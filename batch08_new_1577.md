# Patient Portal Appointments

## TC01 Referral Request Form — Autofill Conflict

- **Work Item ID:** 1577
- **Description:** Verify that Referral Request Form operates correctly when loaded by patient user
- **Precondition:** Patient user is logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Referral Request Form.
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.

## TC02 Two-Factor Login Prompt — Rapid Repeated Taps

- **Work Item ID:** 1577
- **Description:** Verify that Two-Factor Login Prompt operates correctly when loaded by patient user
- **Precondition:** Patient user is logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Two-Factor Login Prompt.
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.

## TC03 Insurance Card Upload — Session Timeout Recovery

- **Work Item ID:** 1577
- **Description:** Verify edge case data handling during Insurance Card Upload execution
- **Precondition:** User profile settings configured with default preferences.
- **Test Step:** 1
- **Test Step Description:** Submit the request form and observe screen update for Insurance Card Upload.
- **Test Step Expected Result:** System logs action correctly and maintains complete session data integrity.

## TC04 Recurring Appointment Setup — Deep Link Entry

- **Work Item ID:** 1577
- **Description:** Verify behavior of Recurring Appointment Setup under standard network load conditions
- **Precondition:** Database populated with active patient appointment records.
- **Test Step:** 1
- **Test Step Description:** Select the target option from 'My Appointments' view for Recurring Appointment Setup.
- **Test Step Expected Result:** Correct data visual tags render cleanly without page overflow.

## TC05 Insurance Eligibility Check — Multi-Device Sync

- **Work Item ID:** 1577
- **Description:** Verify that Insurance Eligibility Check operates correctly when loaded by patient user
- **Precondition:** Patient user is logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Insurance Eligibility Check.
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.
