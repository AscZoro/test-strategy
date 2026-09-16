# Patient Portal Appointments

## TC01 Language Preference Toggle — Concurrent Booking Attempt

- **Work Item ID:** 1576
- **Description:** Verify that Language Preference Toggle operates correctly when loaded by patient user
- **Precondition:** Patient user is logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Language Preference Toggle.
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.

## TC02 Wearable Device Sync — Time Zone Boundary

- **Work Item ID:** 1576
- **Description:** Verify UI validation and error handling for Wearable Device Sync
- **Precondition:** Mock scheduling API server online and reachable.
- **Test Step:** 1
- **Test Step Description:** Execute user interaction sequence corresponding to Wearable Device Sync.
- **Test Step Expected Result:** Appropriate status indicator displays with expected confirmation message.

## TC03 Visit Summary Download — Expired Auth Token

- **Work Item ID:** 1576
- **Description:** Verify behavior of Visit Summary Download under standard network load conditions
- **Precondition:** Database populated with active patient appointment records.
- **Test Step:** 1
- **Test Step Description:** Select the target option from 'My Appointments' view for Visit Summary Download.
- **Test Step Expected Result:** Correct data visual tags render cleanly without page overflow.

## TC04 Waitlist Notification — Expired Auth Token

- **Work Item ID:** 1576
- **Description:** Verify UI validation and error handling for Waitlist Notification
- **Precondition:** Mock scheduling API server online and reachable.
- **Test Step:** 1
- **Test Step Description:** Execute user interaction sequence corresponding to Waitlist Notification.
- **Test Step Expected Result:** Appropriate status indicator displays with expected confirmation message.

## TC05 Lab Result Notification — Partial Form Submission

- **Work Item ID:** 1576
- **Description:** Verify behavior of Lab Result Notification under standard network load conditions
- **Precondition:** Database populated with active patient appointment records.
- **Test Step:** 1
- **Test Step Description:** Select the target option from 'My Appointments' view for Lab Result Notification.
- **Test Step Expected Result:** Correct data visual tags render cleanly without page overflow.
