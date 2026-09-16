# Patient Portal Appointments

## TC001 Local Time Zone Conversion (DUPLICATE of original TC010)

- **Work Item ID:** 1571
- **Description:** Verify appointment times match user local target time zones automatically
- **Precondition:** Server database time stamps persist tracking configurations natively in UTC.
- **Test Step:** 1
- **Test Step Description:** Evaluate display text fields for the specific appointment scheduling elements.
- **Test Step Expected Result:** System automatically translates runtime timestamps into local parameters, rendering output value as 10:00 AM EST without backend data drift.

## TC002 Pagination Control — Concurrent Booking Attempt

- **Work Item ID:** 1571
- **Description:** Verify behavior of Pagination Control under standard network load conditions
- **Precondition:** Database populated with active patient appointment records.
- **Test Step:** 1
- **Test Step Description:** Select the target option from 'My Appointments' view for Pagination Control
- **Test Step Expected Result:** Correct data visual tags render cleanly without page overflow.

## TC003 Pagination Control — Slow Network Retry

- **Work Item ID:** 1571
- **Description:** Verify behavior of Pagination Control under standard network load conditions
- **Precondition:** Database populated with active patient appointment records.
- **Test Step:** 1
- **Test Step Description:** Select the target option from 'My Appointments' view for Pagination Control
- **Test Step Expected Result:** Correct data visual tags render cleanly without page overflow.

## TC004 Cancel Appointment Modal — Browser Back Button

- **Work Item ID:** 1571
- **Description:** Verify that Cancel Appointment Modal operates correctly when loaded by patient user
- **Precondition:** Patient user logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Cancel Appointment Modal
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.

## TC005 Appointment Reminder Toggle — Low Bandwidth Mode

- **Work Item ID:** 1571
- **Description:** Verify edge case data handling during Appointment Reminder Toggle execution
- **Precondition:** User profile settings configured with default preferences.
- **Test Step:** 1
- **Test Step Description:** Submit the request form and observe screen update for Appointment Reminder Toggle
- **Test Step Expected Result:** System logs action correctly and maintains complete session data integrity.
