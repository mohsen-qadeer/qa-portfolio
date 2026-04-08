# Test Cases — Party & Group Bookings

**Platform:** Web & Mobile
**Module:** Party & Group Bookings
**Tool:** JIRA-style Format
**Prepared By:** Mohsen Qadeer

---

## TC-001: Party Size / Headcount Limit Enforcement

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-001                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Headcount Limits                             |
| Test Type       | Functional & Boundary                        |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Admin logged in, venue has defined capacity  |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to group booking creation page     | Form loads correctly                         |
| 2    | Enter party size within allowed limit       | System accepts valid headcount               |
| 3    | Enter party size exactly at limit           | System accepts maximum headcount             |
| 4    | Enter party size exceeding limit            | System blocks booking with error             |
| 5    | Observe error message on exceeding limit    | Error: "Party size exceeds venue capacity"   |
| 6    | Check database for rejected booking         | No record created for exceeded limit         |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Headcount enforced, overflow bookings blocked|
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-002: Deposit Payment at Booking

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-002                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Deposit Payment                              |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Booking form open, deposit option available  |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to group booking page              | Form loads correctly                         |
| 2    | Fill in all booking details                 | Fields accept valid input                    |
| 3    | Select "Pay Deposit" option                 | Deposit amount displayed correctly           |
| 4    | Enter valid payment details                 | Payment fields accept input                  |
| 5    | Click "Confirm Booking" button              | Deposit payment processes successfully       |
| 6    | Verify deposit record in database           | Record created with deposit amount and status|
| 7    | Check remaining balance displayed           | Correct remaining balance shown to user      |
| 8    | Verify deposit confirmation email sent      | Email received with deposit and balance info |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Deposit recorded, balance tracked in system  |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-003: Full Payment at Booking

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-003                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Full Payment                                 |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Booking form open, full payment option active|

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to group booking page              | Form loads correctly                         |
| 2    | Fill in all booking details                 | Fields accept valid input                    |
| 3    | Select "Pay Full Amount" option             | Full amount displayed correctly              |
| 4    | Enter valid payment details                 | Payment fields accept input                  |
| 5    | Click "Confirm Booking" button              | Full payment processes successfully          |
| 6    | Verify payment record in database           | Record created with full amount and status   |
| 7    | Verify booking status updated to "Paid"     | Booking marked as fully paid in system       |
| 8    | Check full payment confirmation email       | Email received with complete payment details |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Full payment recorded, booking confirmed     |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-004: Booking Confirmation & Notifications

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-004                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Booking Confirmation                         |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Booking completed successfully               |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Complete a group booking                    | Booking confirmed in system                  |
| 2    | Check confirmation screen                   | Booking ID and details displayed             |
| 3    | Verify confirmation email to customer       | Email received with full booking details     |
| 4    | Verify notification to admin/instructor     | Admin and instructor notified of new booking |
| 5    | Check in-app notification                   | Notification visible in dashboard            |
| 6    | Verify all notification content accurate    | Date, time, venue, headcount all correct     |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | All parties notified with correct details    |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-005: Booking Cancellation

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-005                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Cancellation                                 |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Active booking exists in system              |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to existing booking details        | Booking details load correctly               |
| 2    | Click "Cancel Booking" button               | Cancellation confirmation dialog appears     |
| 3    | Confirm cancellation                        | Booking cancelled successfully               |
| 4    | Verify booking status updated               | Status changed to "Cancelled" in system      |
| 5    | Check database for cancellation record      | Record updated with cancelled status         |
| 6    | Verify cancellation email sent              | Email received with cancellation details     |
| 7    | Check refund triggered if applicable        | Refund initiated based on cancellation policy|

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Booking cancelled, refund triggered if due   |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-006: Booking Rescheduling

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-006                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Rescheduling                                 |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Active booking exists, new slot available    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to existing booking details        | Booking details load correctly               |
| 2    | Click "Reschedule Booking" button           | Rescheduling options appear                  |
| 3    | Select new available date and time          | New slot selected successfully               |
| 4    | Confirm rescheduling                        | Booking updated to new date and time         |
| 5    | Verify old slot released in system          | Previous slot available for new bookings     |
| 6    | Check database for updated booking record   | Record updated with new date and time        |
| 7    | Verify rescheduling notification sent       | Email received with updated booking details  |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Booking rescheduled, all parties notified    |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-007: Special Requests & Notes

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-007                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Special Requests                             |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Medium                                       |
| Preconditions   | Booking form open, special requests field    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to group booking form              | Form loads correctly                         |
| 2    | Locate special requests / notes field       | Field visible and accessible                 |
| 3    | Enter special request text                  | Field accepts text input correctly           |
| 4    | Enter maximum character limit text          | Field accepts up to character limit          |
| 5    | Exceed character limit                      | Field stops accepting or shows warning       |
| 6    | Complete and confirm booking                | Special request saved with booking           |
| 7    | Verify request visible to admin/instructor  | Request displayed in booking details         |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Special request saved and visible to team    |
| Severity        | Medium                                       |
| Status          | Pass                                         |

---

## TC-008: Instructor & Venue Assignment

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-008                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Instructor & Venue Assignment                |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, instructors and venues exist|

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to group booking form              | Form loads correctly                         |
| 2    | Select venue from available options         | Venue list loads and selection works         |
| 3    | Assign instructor to booking                | Instructor list loads and selection works    |
| 4    | Verify instructor availability for slot     | System checks and confirms availability      |
| 5    | Attempt to assign unavailable instructor    | System blocks with availability error        |
| 6    | Confirm booking with valid assignments      | Booking saved with instructor and venue      |
| 7    | Verify instructor notified of assignment    | Instructor receives booking notification     |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Booking assigned to correct instructor/venue |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-009: Mobile Group Booking — Responsive View

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-009                                       |
| Module          | Party & Group Bookings                       |
| Sub-Module      | Mobile Responsiveness                        |
| Test Type       | UI / Compatibility                           |
| Platform        | Mobile (iOS & Android)                       |
| Priority        | High                                         |
| Preconditions   | User accessing booking form via mobile       |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Open group booking page on mobile           | Page renders correctly on small screen       |
| 2    | Check all form fields visible               | No fields cut off or hidden                  |
| 3    | Tap each input field                        | Mobile keyboard appears correctly            |
| 4    | Fill in all booking details on mobile       | All fields accept input correctly            |
| 5    | Complete payment on mobile                  | Payment processes successfully               |
| 6    | Verify booking confirmation on mobile       | Confirmation message displays correctly      |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Group booking completed successfully on mobile|
| Severity        | High                                         |
| Status          | Pass                                         |
