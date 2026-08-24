# Patient Portal Test Cases

## TC001: Chronological Sorting
- **Work Item ID:** 1571
- **Module:** Patient Portal Appointments
- **Description:** Verify upcoming appointments display ordered by date/time in ascending chronological order.
- **Precondition:** Patient user is logged in. Multiple scheduled active appointments populated.
- **Test Step:** Navigate directly into the 'My Appointments' page grid dashboard view.
- **Expected Result:** Portal interface correctly orders appointments chronologically ascending (earliest upcoming date maps first at top row position).

## TC004: Accessibility - WCAG AA
- **Work Item ID:** 1571
- **Module:** Patient Portal Appointments
- **Description:** Verify screen reader element tag descriptions on custom grid cards meet compliance standards.
- **Test Step:** Inspect keyboard tab focus sequence traversals across the list elements components.
- **Expected Result:** All interactive containers emit accurate ARIA accessibility labels matching standard WCAG AA specification perimeters cleanly.

## TC007: Cancelled Expiry Visibility
- **Work Item ID:** 1571
- **Module:** Patient Portal Appointments
- **Description:** Verify visibility lifecycle properties for cancelled appointments past their expiration.
- **Precondition:** Current mock test framework execution time maps to 2026-07-16 13:00.
- **Test Step:** Trigger page view lookup refresh command parameters.
- **Expected Result:** Cancelled appointments automatically stop rendering in upcoming list sections completely once their originally scheduled hour has passed.
