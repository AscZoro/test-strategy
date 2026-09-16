# Patient Portal Appointments

## TC13 Payment Method Update — Partial Form Submission

- **Work Item ID:** 1575
- **Description:** Verify that Payment Method Update operates correctly when loaded by patient user
- **Precondition:** Patient user is logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Payment Method Update.
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.

## TC14 Recurring Appointment Setup — Time Zone Boundary

- **Work Item ID:** 1575
- **Description:** Verify edge case data handling during Recurring Appointment Setup execution
- **Precondition:** User profile settings configured with default preferences.
- **Test Step:** 1
- **Test Step Description:** Submit the request form and observe screen update for Recurring Appointment Setup.
- **Test Step Expected Result:** System logs action correctly and maintains complete session data integrity.

## TC15 Vaccine Record Display — Concurrent Booking Attempt

- **Work Item ID:** 1575
- **Description:** Verify that Vaccine Record Display operates correctly when loaded by patient user
- **Precondition:** Patient user is logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Vaccine Record Display.
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.

## TC16 Vaccine Record Display — Push Notification Deep Link

- **Work Item ID:** 1575
- **Description:** Verify UI validation and error handling for Vaccine Record Display
- **Precondition:** Mock scheduling API server online and reachable.
- **Test Step:** 1
- **Test Step Description:** Execute user interaction sequence corresponding to Vaccine Record Display.
- **Test Step Expected Result:** Appropriate status indicator displays with expected confirmation message.

## TC17 Language Preference Toggle — Multi-Device Sync

- **Work Item ID:** 1575
- **Description:** Verify edge case data handling during Language Preference Toggle execution
- **Precondition:** User profile settings configured with default preferences.
- **Test Step:** 1
- **Test Step Description:** Submit the request form and observe screen update for Language Preference Toggle.
- **Test Step Expected Result:** System logs action correctly and maintains complete session data integrity.
