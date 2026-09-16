# Patient Portal Appointments

## TC18 Guardian Access Control — Deep Link Entry

- **Work Item ID:** 1575
- **Description:** Verify edge case data handling during Guardian Access Control execution
- **Precondition:** User profile settings configured with default preferences.
- **Test Step:** 1
- **Test Step Description:** Submit the request form and observe screen update for Guardian Access Control.
- **Test Step Expected Result:** System logs action correctly and maintains complete session data integrity.

## TC19 Provider Rating Submission — Guest Checkout Flow

- **Work Item ID:** 1575
- **Description:** Verify behavior of Provider Rating Submission under standard network load conditions
- **Precondition:** Database populated with active patient appointment records.
- **Test Step:** 1
- **Test Step Description:** Select the target option from 'My Appointments' view for Provider Rating Submission.
- **Test Step Expected Result:** Correct data visual tags render cleanly without page overflow.
