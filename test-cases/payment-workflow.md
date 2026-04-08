# Test Cases — Payment Workflow

**Platform:** Web & Mobile
**Module:** Payment Processing
**Tool:** JIRA-style Format
**Prepared By:** Mohsen Qadeer

---

## TC-001: Successful Payment Processing

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-001                                       |
| Module          | Payments                                     |
| Sub-Module      | Payment Processing                           |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | User is logged in, has items in cart         |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to checkout page                   | Page loads with correct order summary        |
| 2    | Enter valid payment details                 | Fields accept input correctly                |
| 3    | Click "Pay Now" button                      | Payment processing spinner appears           |
| 4    | Wait for payment confirmation               | Success message displayed with order ID      |
| 5    | Check database for payment record           | Record created with correct amount & status  |
| 6    | Verify payment confirmation email           | Email received with invoice details          |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Payment record in DB, invoice emailed        |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-002: Payment With Invalid Card Details

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-002                                       |
| Module          | Payments                                     |
| Sub-Module      | Card Validation                              |
| Test Type       | Negative                                     |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | User is logged in, on checkout page          |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to checkout page                   | Page loads correctly                         |
| 2    | Enter invalid card number (e.g. 1234)       | Field accepts input temporarily              |
| 3    | Enter expired card date                     | Field accepts input temporarily              |
| 4    | Click "Pay Now" button                      | Payment does not process                     |
| 5    | Observe error message                       | Error: "Invalid card details"                |
| 6    | Check database                              | No payment record created                    |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | No charge made, user prompted to retry       |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-003: Duplicate Payment Prevention

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-003                                       |
| Module          | Payments                                     |
| Sub-Module      | Duplicate Transaction                        |
| Test Type       | Negative                                     |
| Platform        | Web & Mobile                                 |
| Priority        | Critical                                     |
| Preconditions   | User has already completed payment           |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Complete a successful payment               | Payment confirmed                            |
| 2    | Press browser back button                   | Returns to checkout page                     |
| 3    | Click "Pay Now" again                       | System detects duplicate transaction         |
| 4    | Observe system response                     | Error: "Payment already processed"           |
| 5    | Check database                              | Single payment record only                   |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | No duplicate charge, single record in DB     |
| Severity        | Critical                                     |
| Status          | Pass                                         |

---

## TC-004: Partial Payment Processing

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-004                                       |
| Module          | Payments                                     |
| Sub-Module      | Partial Payment                              |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Platform supports partial payments           |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to checkout page                   | Page loads with full amount due              |
| 2    | Select partial payment option               | Partial amount field appears                 |
| 3    | Enter valid partial amount                  | System accepts partial amount                |
| 4    | Click "Pay Now" button                      | Partial payment processes successfully       |
| 5    | Check remaining balance displayed           | Correct remaining balance shown              |
| 6    | Verify database record                      | Partial payment recorded with balance due    |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Partial payment recorded, balance tracked    |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-005: Payment Refund Processing

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-005                                       |
| Module          | Payments                                     |
| Sub-Module      | Refund                                       |
| Test Type       | Functional                                   |
| Platform        | Web & Mobile                                 |
| Priority        | High                                         |
| Preconditions   | Completed payment exists in system           |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Navigate to payment history                 | All payments listed correctly                |
| 2    | Select completed payment                    | Payment details displayed                    |
| 3    | Click "Request Refund" button               | Refund confirmation dialog appears           |
| 4    | Confirm refund request                      | Refund initiated successfully                |
| 5    | Check database for refund record            | Refund record created with correct amount    |
| 6    | Verify refund confirmation email            | Email received with refund details           |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Refund processed, record updated in DB       |
| Severity        | High                                         |
| Status          | Pass                                         |

---

## TC-006: Mobile Payment — Responsive Checkout

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Test Case ID    | TC-006                                       |
| Module          | Payments                                     |
| Sub-Module      | Mobile Responsiveness                        |
| Test Type       | UI / Compatibility                           |
| Platform        | Mobile (iOS & Android)                       |
| Priority        | High                                         |
| Preconditions   | User accessing checkout via mobile browser   |

### Steps

| Step | Action                                      | Expected Result                              |
|------|---------------------------------------------|----------------------------------------------|
| 1    | Open checkout page on mobile browser        | Page renders correctly on small screen       |
| 2    | Check all payment fields visible            | No fields cut off or hidden                  |
| 3    | Tap card number field                       | Numeric keyboard appears                     |
| 4    | Fill in all payment details                 | All fields accept input correctly            |
| 5    | Click "Pay Now" on mobile                   | Payment processes successfully               |
| 6    | Verify success message on mobile view       | Message displays correctly on mobile screen  |

| Field           | Details                                      |
|-----------------|----------------------------------------------|
| Post Conditions | Payment completed successfully via mobile    |
| Severity        | High                                         |
| Status          | Pass                                         |
