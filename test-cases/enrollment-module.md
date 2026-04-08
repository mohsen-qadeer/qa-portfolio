# Test Cases — Enrollment Module

**Platform:** Web & Mobile
**Module:** Enrollment & Student Registration
**Tool:** JIRA-style Format
**Prepared By:** Mohsen Qadeer

---

## TC-001: Successful Student Enrollment

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-001                                       |
| Module          | Enrollment                                   |
| Sub-Module      | Student Registration                         |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | User is on registration page, no existing account |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to enrollment/registration page    | Page loads correctly on web and mobile       |
| 2    | Fill in all required fields (name, email, phone) | All fields accept valid input           |
| 3    | Select course/class from dropdown           | Available courses listed and selectable      |
| 4    | Click "Enroll" or "Submit" button           | Success message displayed to user            |
| 5    | Check database for new student record       | Record created with correct details          |
| 6    | Verify confirmation email sent              | Email received with enrollment details       |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Student record exists in DB, email triggered |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-002: Enrollment With Missing Required Fields

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-002                                       |
| Module          | Enrollment                                   |
| Sub-Module      | Field Validation                             |
| Test Type       | Negative                                     |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | User is on registration page                 |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to enrollment page                 | Page loads correctly                         |
| 2    | Leave required fields empty                 | Fields remain empty                          |
| 3    | Click "Enroll" or "Submit" button           | Form does not submit                         |
| 4    | Observe validation messages                 | Error messages shown on all required fields  |
| 5    | Check database                              | No new record created                        |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | No record created, user stays on form        |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-003: Duplicate Enrollment Prevention

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-003                                       |
| Module          | Enrollment                                   |
| Sub-Module      | Duplicate Validation                         |
| Test Type       | Negative                                     |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Student already enrolled in selected course  |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Login with already enrolled student account | Login successful                             |
| 2    | Navigate to enrollment page                 | Page loads correctly                         |
| 3    | Select same course already enrolled in      | System detects existing enrollment           |
| 4    | Click "Enroll" button                       | Error message: "Already enrolled in this course" |
| 5    | Check database                              | No duplicate record created                  |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Single enrollment record remains in DB       |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-004: Mobile Enrollment — Responsive Layout

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-004                                       |
| Module          | Enrollment                                   |
| Sub-Module      | Mobile Responsiveness                        |
| Test Type       | UI / Compatibility                           |
| Platform        | Mobile (iOS & Android)                       |
| Priority        | Medium                                       |
| Preconditions   | User accessing platform via mobile browser   |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Open enrollment page on mobile browser      | Page renders correctly on small screen       |
| 2    | Check all form fields are visible           | No fields cut off or hidden                  |
| 3    | Tap each input field                        | Mobile keyboard appears correctly            |
| 4    | Fill in all details and submit              | Form submits successfully on mobile          |
| 5    | Verify success message on mobile view       | Message displays correctly on mobile screen  |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Enrollment completed successfully via mobile |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-005: Enrollment With Invalid Email Format

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-005                                       |
| Module          | Enrollment                                   |
| Sub-Module      | Email Validation                             |
| Test Type       | Negative                                     |
| Platform        | Web & Mobile                                 |
| Priority        | Medium                                       |
| Preconditions   | User is on registration page                 |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to enrollment page                 | Page loads correctly                         |
| 2    | Enter invalid email (e.g. "mohsen@")        | Field accepts the input temporarily          |
| 3    | Fill remaining fields with valid data       | Other fields accept input                    |
| 4    | Click "Enroll" button                       | Form does not submit                         |
| 5    | Observe validation message on email field   | Error: "Please enter a valid email address"  |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | No record created, user prompted to fix email|
| Severity        | Medium                                       |
| Status          | Pass                                         |
