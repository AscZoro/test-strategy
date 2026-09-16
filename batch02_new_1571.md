# Patient Portal Appointments

## TC006 Cancel Appointment Modal — Low Bandwidth Mode

- **Work Item ID:** 1571
- **Description:** Verify that Cancel Appointment Modal operates correctly when loaded by patient user
- **Precondition:** Patient user logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Cancel Appointment Modal
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.

## TC007 Mobile Responsive Grid — Expired Auth Token

- **Work Item ID:** 1571
- **Description:** Verify UI validation and error handling for Mobile Responsive Grid
- **Precondition:** Mock scheduling API server online and reachable.
- **Test Step:** 1
- **Test Step Description:** Execute user interaction sequence corresponding to Mobile Responsive Grid
- **Test Step Expected Result:** Appropriate status indicator displays with expected confirmation message.

## TC008 Timezone Sync — Concurrent Booking Attempt

- **Work Item ID:** 1571
- **Description:** Verify that Timezone Sync operates correctly when loaded by patient user
- **Precondition:** Patient user logged in with valid session token.
- **Test Step:** 1
- **Test Step Description:** Navigate to the Patient Portal dashboard and trigger Timezone Sync
- **Test Step Expected Result:** System successfully processes request and updates UI state within 2 seconds.

## TC009 Session Timeout Handling — Stale Cache Reload

- **Work Item ID:** 1571
- **Description:** Verify edge case data handling during Session Timeout Handling execution
- **Precondition:** User profile settings configured with default preferences.
- **Test Step:** 1
- **Test Step Description:** Submit the request form and observe screen update for Session Timeout Handling
- **Test Step Expected Result:** System logs action correctly and maintains complete session data integrity.
