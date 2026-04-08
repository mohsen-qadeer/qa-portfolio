# Test Cases — Class & Event Creation

**Platform:** Web & Mobile
**Module:** Class & Event Creation
**Tool:** JIRA-style Format
**Prepared By:** Mohsen Qadeer

---

## TC-001: Create Class With Instructor Assignment

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-001                                       |
| Module          | Class & Event Creation                       |
| Sub-Module      | Class Creation                               |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Admin logged in, instructors exist in system |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Class Creation page             | Form loads correctly                         |
| 2    | Enter class name and description            | Fields accept input correctly                |
| 3    | Assign instructor from dropdown             | Instructor list loads and selection works    |
| 4    | Set class date and time                     | Date and time fields accept valid input      |
| 5    | Click "Create Class" button                 | Class created successfully                   |
| 6    | Verify class appears in system              | New class visible in class listing           |
| 7    | Check database for class record             | Record created with correct instructor       |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Class created and assigned to instructor     |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-002: Set Class Schedule With Recurring Sessions

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-002                                       |
| Module          | Class & Event Creation                       |
| Sub-Module      | Recurring Schedule                           |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, class creation form open    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Class Creation page             | Form loads correctly                         |
| 2    | Enter class details                         | Fields accept input correctly                |
| 3    | Select "Recurring" schedule option          | Recurring options appear                     |
| 4    | Set frequency (daily/weekly/monthly)        | Frequency options selectable                 |
| 5    | Set recurring end date                      | End date field accepts valid input           |
| 6    | Click "Create Class" button                 | All recurring sessions created               |
| 7    | Verify all sessions appear in calendar      | Sessions visible on correct dates            |
| 8    | Check database for all session records      | All recurring records created correctly      |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | All recurring sessions created in system     |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-003: Class Capacity Limit Enforcement

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-003                                       |
| Module          | Class & Event Creation                       |
| Sub-Module      | Capacity Limits                              |
| Test Type       | Functional & Boundary                        |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Class created with defined capacity limit    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Create class with capacity limit of 10      | Class created with limit saved               |
| 2    | Enroll 10 students into the class           | All 10 enrollments accepted                  |
| 3    | Attempt to enroll 11th student              | System blocks enrollment                     |
| 4    | Observe error message                       | Error: "Class is full"                       |
| 5    | Check database for enrollment count         | Exactly 10 records exist, no overflow        |
| 6    | Verify capacity indicator on class listing  | Class shows as "Full" in listing             |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Capacity enforced, no overflow enrollments   |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-004: Location & Room Assignment

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-004                                       |
| Module          | Class & Event Creation                       |
| Sub-Module      | Location Assignment                          |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, locations exist in system   |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Class Creation page             | Form loads correctly                         |
| 2    | Enter class details                         | Fields accept input correctly                |
| 3    | Select location from dropdown               | Location list loads correctly                |
| 4    | Select specific room at location            | Room options load based on location          |
| 5    | Click "Create Class" button                 | Class created with location and room         |
| 6    | Verify location visible on class details    | Location and room display correctly          |
| 7    | Attempt to double-book same room            | System blocks double booking with error      |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Class assigned to correct location and room  |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-005: Online vs In-Person Class Creation

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-005                                       |
| Module          | Class & Event Creation                       |
| Sub-Module      | Online vs In-Person                          |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, class creation form open    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Class Creation page             | Form loads correctly                         |
| 2    | Select "Online" class type                  | Online link/meeting field appears            |
| 3    | Enter online meeting link                   | Link field accepts valid URL                 |
| 4    | Save class as online                        | Class saved with online meeting link         |
| 5    | Create second class as "In-Person"          | Location and room fields appear              |
| 6    | Verify correct fields shown per type        | Online shows link, In-Person shows location  |
| 7    | Check student view for both class types     | Students see correct details per class type  |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Both class types created and display correctly|
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-006: Event Registration & Ticketing

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-006                                       |
| Module          | Class & Event Creation                       |
| Sub-Module      | Event Registration & Ticketing               |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Admin logged in, event created in system     |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Event Creation page             | Form loads correctly                         |
| 2    | Create event with ticketing enabled         | Ticket options appear                        |
| 3    | Set ticket price and quantity               | Fields accept valid input                    |
| 4    | Publish event                               | Event visible to students for registration   |
| 5    | Register as student and purchase ticket     | Ticket purchased and confirmed               |
| 6    | Verify ticket record in database            | Ticket record created with correct details   |
| 7    | Check ticket confirmation email sent        | Email received with ticket details           |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Event ticket purchased and recorded in DB    |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-007: Student Notifications for New Class

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-007                                       |
| Module          | Class & Event Creation                       |
| Sub-Module      | Student Notifications                        |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Students enrolled, new class created         |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Admin creates new class                     | Class created successfully                   |
| 2    | Assign enrolled students to class           | Students assigned correctly                  |
| 3    | Publish class                               | System triggers notification to students     |
| 4    | Check student email notifications           | Email received with class details            |
| 5    | Check in-app notifications                  | Notification visible in student dashboard    |
| 6    | Verify notification content is accurate     | Class name, date, time, location all correct |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | All students notified with correct details   |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-008: Mobile Class Creation — Responsive View

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-008                                       |
| Module          | Class & Event Creation                       |
| Sub-Module      | Mobile Responsiveness                        |
| Test Type       | UI / Compatibility                           |
| Platform        | Mobile (iOS & Android)                       |
| Priority        | High                                         |
| Preconditions   | Admin accessing class creation via mobile    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Open class creation page on mobile          | Page renders correctly on small screen       |
| 2    | Check all form fields visible               | No fields cut off or hidden                  |
| 3    | Tap each input field                        | Mobile keyboard appears correctly            |
| 4    | Fill in all class details                   | All fields accept input on mobile            |
| 5    | Click "Create Class" on mobile              | Class created successfully via mobile        |
| 6    | Verify class appears in system              | New class visible in listing on mobile       |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Class created successfully via mobile        |
| Severity        | High                                         |
| Status          | Pass                                         |
