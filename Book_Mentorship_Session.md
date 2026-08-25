# Use-Case Flow Specification

## UC-03 – Book Mentorship Session

### 1. Use-Case Information

| Field | Details |
|---|---|
| **Use Case ID** | UC-03 |
| **Use Case Name** | Book Mentorship Session |
| **Primary Actor** | Student Mentee |
| **Supporting Actor** | Alumni Mentor |
| **External Supporting Actor** | Calendar & Meeting Service |
| **Goal** | Allow a student to book an available mentorship session with a suitable alumni mentor without double-booking. |

### 2. Preconditions

1. The student is registered and logged into the platform.
2. A suitable alumni mentor has been identified.
3. The mentor has at least one available session slot.
4. The Calendar & Meeting Service is available.

### 3. Postconditions

**On Success**
1. A mentorship session is created.
2. The selected mentor slot is marked unavailable.
3. A calendar event is created for the student and mentor.
4. A meeting link is attached to the event.
5. The student receives booking confirmation.

**On Failure**
1. No conflicting booking is created.
2. The original slot remains available if the booking fails before confirmation.
3. The student is informed of the failure and can select another slot.

### 4. Main Success Scenario

1. **Student:** Selects a suitable alumni mentor.
2. **System:** Displays the mentor's profile and available session slots.
3. **Student:** Selects an available mentorship slot.
4. **System:** Checks that the selected slot is still available.
5. **System:** Reserves the slot for the booking transaction.
6. **System:** Creates the mentorship session.
7. **System:** Requests the Calendar & Meeting Service to create calendar events and generate a meeting link.
8. **Calendar & Meeting Service:** Creates the calendar event(s) and returns the meeting link.
9. **System:** Marks the mentor's selected slot as unavailable.
10. **System:** Displays/sends the booking confirmation to the student and mentor.
11. **Use case ends successfully.**

### 5. Alternate Flow – Double-Booking / Slot Becomes Unavailable

**Condition:** Another student books the selected slot before the current student's booking is confirmed.

1. At Step 4, the system checks the selected slot.
2. The system detects that the slot is no longer available.
3. The system does not create a conflicting booking.
4. The system displays: **“The selected time slot is no longer available.”**
5. The system displays the mentor's remaining available slots.
6. The student selects another available slot.
7. The system repeats the availability check.
8. If the new slot is available, the flow continues from Step 5 of the Main Success Scenario.

### 6. Related Requirements

- **FR-001:** Intelligent Mentor Matching
- **FR-002:** Mentor Profile and Availability Viewing
- **FR-003:** Mentorship Session Booking
- **NFR-001:** Performance & Security
- **NFR-002:** Availability and Reliability
