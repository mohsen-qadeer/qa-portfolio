# Test Cases — Attendance Tracking

**Platform:** Web & Mobile
**Module:** Attendance Tracking
**Tool:** JIRA-style Format
**Prepared By:** Mohsen Qadeer

---

## TC-001: Mark Student Present

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-001                                       |
| Module          | Attendance                                   |
| Sub-Module      | Mark Present / Absent                        |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Instructor logged in, class session active   |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to active class session            | Class roster loads with all students         |
| 2    | Locate student in attendance list           | Student name visible in roster               |
| 3    | Mark student as "Present"                   | Status updates to Present immediately        |
| 4    | Verify status change saved                  | Present status persists after page refresh   |
| 5    | Check database for attendance record        | Record created with correct status and time  |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Attendance record saved correctly in DB      |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-002: Mark Student Absent

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-002                                       |
| Module          | Attendance                                   |
| Sub-Module      | Mark Present / Absent                        |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Instructor logged in, class session active   |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to active class session            | Class roster loads with all students         |
| 2    | Locate student in attendance list           | Student name visible in roster               |
| 3    | Mark student as "Absent"                    | Status updates to Absent immediately         |
| 4    | Verify status change saved                  | Absent status persists after page refresh    |
| 5    | Check database for attendance record        | Record created with correct absent status    |
| 6    | Verify absence notification triggered       | Student notified of absence via email/system |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Absent record saved, notification triggered  |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-003: Late Arrival Marking

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-003                                       |
| Module          | Attendance                                   |
| Sub-Module      | Late Arrivals                                |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Instructor logged in, class session active   |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to active class session            | Class roster loads correctly                 |
| 2    | Locate student who arrived late             | Student visible in roster                    |
| 3    | Mark student as "Late"                      | Status updates to Late immediately           |
| 4    | Verify late arrival time is recorded        | System captures exact time of late marking   |
| 5    | Check database for late arrival record      | Record saved with Late status and timestamp  |
| 6    | Verify late arrival appears in reports      | Attendance report reflects Late status       |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Late record saved with correct timestamp     |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-004: Instructor Attendance Marking

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-004                                       |
| Module          | Attendance                                   |
| Sub-Module      | Instructor Attendance                        |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, class session scheduled     |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to class session details           | Session details load correctly               |
| 2    | Locate instructor attendance section        | Instructor roster displayed                  |
| 3    | Mark instructor as Present / Absent         | Status updates immediately                   |
| 4    | Verify instructor status saved in DB        | Record created with correct status           |
| 5    | Check instructor attendance in reports      | Report reflects instructor attendance        |
| 6    | Verify absent instructor triggers alert     | Admin notified of instructor absence         |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Instructor attendance recorded accurately    |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-005: Automated Attendance via Check-In

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-005                                       |
| Module          | Attendance                                   |
| Sub-Module      | Automated Check-In                           |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Check-in system active, class session live   |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Student opens check-in page on mobile       | Check-in page loads correctly                |
| 2    | Student completes check-in action           | System registers check-in with timestamp     |
| 3    | Verify attendance auto-marked as Present    | Status updated automatically without manual  |
| 4    | Check database for automated record         | Record created with check-in timestamp       |
| 5    | Verify check-in within class time window    | Only valid check-ins within window accepted  |
| 6    | Attempt check-in outside class time window  | System rejects late check-in with message    |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Automated attendance recorded accurately     |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-006: Attendance Override by Admin

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-006                                       |
| Module          | Attendance                                   |
| Sub-Module      | Admin Override                               |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, attendance record exists    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to existing attendance record      | Record displays current status               |
| 2    | Click "Edit" or "Override" on record        | Edit mode activates                          |
| 3    | Change attendance status                    | New status selected successfully             |
| 4    | Add override reason/note                    | Note field accepts input                     |
| 5    | Save changes                                | Updated status saved with override note      |
| 6    | Verify audit trail in database              | Override logged with admin name and reason   |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Attendance updated with full audit trail     |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-007: Mobile Attendance — Responsive View

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-007                                       |
| Module          | Attendance                                   |
| Sub-Module      | Mobile Responsiveness                        |
| Test Type       | UI / Compatibility                           |
| Platform        | Mobile (iOS & Android)                       |
| Priority        | High                                         |
| Preconditions   | Instructor accessing attendance via mobile   |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Open attendance page on mobile browser      | Page renders correctly on small screen       |
| 2    | Check student roster is fully visible       | All student names visible without scrolling  |
| 3    | Tap Present / Absent / Late buttons         | Buttons respond correctly to touch           |
| 4    | Mark attendance for multiple students       | All statuses saved correctly                 |
| 5    | Verify data saved after mobile session      | All records persist in database              |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Attendance marked successfully via mobile    |
| Severity        | High                                         |
| Status          | Pass                                         |
