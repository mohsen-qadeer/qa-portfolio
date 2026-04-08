# Test Cases — Reporting Module

**Platform:** Web & Mobile
**Module:** Reporting & Analytics
**Tool:** JIRA-style Format
**Prepared By:** Mohsen Qadeer

---

## TC-001: Student Enrollment Report Generation

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-001                                       |
| Module          | Reporting                                    |
| Sub-Module      | Enrollment Reports                           |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, enrollments exist in system |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Reports section                 | Reports dashboard loads correctly            |
| 2    | Select "Enrollment Report"                  | Enrollment report options displayed          |
| 3    | Select date range filter                    | Date picker appears and accepts input        |
| 4    | Click "Generate Report"                     | Report generates with correct data           |
| 5    | Verify student count matches database       | Count matches DB records exactly             |
| 6    | Check all columns display correctly         | Name, course, date, status all visible       |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Report displays accurate enrollment data     |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-002: Payment & Revenue Report Generation

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-002                                       |
| Module          | Reporting                                    |
| Sub-Module      | Payment & Revenue Reports                    |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | Admin logged in, payments exist in system    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Reports section                 | Reports dashboard loads correctly            |
| 2    | Select "Payment & Revenue Report"           | Report options displayed                     |
| 3    | Apply date range filter                     | Filter accepts valid date range              |
| 4    | Click "Generate Report"                     | Report generates with correct totals         |
| 5    | Verify total revenue matches DB records     | Amounts match database exactly               |
| 6    | Check refunds and partial payments included | All transaction types reflected correctly    |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Revenue report reflects accurate financials  |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-003: Attendance Report Generation

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-003                                       |
| Module          | Reporting                                    |
| Sub-Module      | Attendance Reports                           |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, attendance records exist    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Reports section                 | Reports dashboard loads correctly            |
| 2    | Select "Attendance Report"                  | Attendance report options displayed          |
| 3    | Filter by class, date range, or student     | Filters apply correctly                      |
| 4    | Click "Generate Report"                     | Report generates with correct attendance data|
| 5    | Verify present/absent counts match DB       | Counts match database records exactly        |
| 6    | Check student names and class details       | All details display correctly                |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Attendance report reflects accurate records  |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-004: Class Performance Report

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-004                                       |
| Module          | Reporting                                    |
| Sub-Module      | Class Performance                            |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, class data exists           |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to Reports section                 | Reports dashboard loads correctly            |
| 2    | Select "Class Performance Report"           | Report options displayed                     |
| 3    | Select specific class or instructor         | Filter applies correctly                     |
| 4    | Click "Generate Report"                     | Report generates with performance metrics    |
| 5    | Verify student scores and completion rates  | Data matches database records                |
| 6    | Check instructor and class details          | All details display correctly                |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Performance report reflects accurate data    |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-005: Custom Date Range Filtering

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-005                                       |
| Module          | Reporting                                    |
| Sub-Module      | Date Range Filter                            |
| Test Type       | Functional & Boundary                        |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Admin logged in, data exists across dates    |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to any report                      | Report options displayed                     |
| 2    | Enter valid custom date range               | Date range accepted correctly                |
| 3    | Click "Generate Report"                     | Report shows data within selected range only |
| 4    | Enter start date later than end date        | Error: "Invalid date range"                  |
| 5    | Enter future date range                     | Report shows no data or appropriate message  |
| 6    | Enter single day date range                 | Report shows that day's data only            |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Reports filtered accurately by date range    |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-006: Export Report to PDF

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-006                                       |
| Module          | Reporting                                    |
| Sub-Module      | PDF Export                                   |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Report generated and displayed on screen     |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Generate any report                         | Report displays correctly on screen          |
| 2    | Click "Export to PDF" button                | PDF download initiates                       |
| 3    | Open downloaded PDF file                    | PDF opens without errors                     |
| 4    | Verify all data matches screen report       | PDF data matches on-screen report exactly    |
| 5    | Check PDF formatting and layout             | All columns, headers, totals display cleanly |
| 6    | Test on mobile browser                      | PDF downloads correctly on mobile            |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | PDF exported with accurate and clean data    |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-007: Export Report to Excel

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-007                                       |
| Module          | Reporting                                    |
| Sub-Module      | Excel Export                                 |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Report generated and displayed on screen     |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Generate any report                         | Report displays correctly on screen          |
| 2    | Click "Export to Excel" button              | Excel file download initiates                |
| 3    | Open downloaded Excel file                  | File opens without errors                    |
| 4    | Verify all data matches screen report       | Excel data matches on-screen report exactly  |
| 5    | Check columns, headers and totals           | All data structured correctly in Excel       |
| 6    | Test large data export                      | Large dataset exports without timeout        |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Excel exported with accurate structured data |
| Severity        | High                                         |
| Status          | Pass                                         |
