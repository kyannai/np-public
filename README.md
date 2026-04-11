# Normanton Park (MCST 4932) -- Forms Digitisation Analysis

**Prepared:** 11 April 2026
**Scope:** Paper-to-digital migration via Hilife CMS
**MCST:** 4932

---

## Table of Contents

1. [Overview](#1-overview)
2. [Paper Forms (A-L)](#2-paper-forms-a-l)
3. [E-Form Design](#3-e-form-design)
4. [Workflows](#4-workflows)
5. [Action Items](#5-action-items)

---

## 1. Overview

Normanton Park condominium (MCST 4932) is migrating its suite of twelve paper-based resident application forms to the Hilife CMS digital platform. The paper forms cover renovation permits, moving requests, vehicle registration, access cards, facility bookings, and occupancy registration, all of which currently require physical submission, manual processing by the Management Agent (MA), and cheque-based deposit collection.

Hilife CMS provides two modules relevant to this migration:

- **E-Form Module** -- for application submissions with approval workflows, reply threads, and signature collection.
- **Facility Booking Module** -- for venue reservations with integrated deposit collection via credit card hold, booking fees, and automated refund lifecycle.

**Current state:** Nine draft e-forms have been created in Hilife, but only the EV Questionnaire (a survey, not an application form) has been published. The Facility Booking module is already operational for the Dining Pavilions, Function Rooms, and Tennis Court. Significant gaps remain in field completeness, payment handling, and workflow coverage across the draft e-forms.

---

## 2. Paper Forms (A-L)

### 2.1 Inventory

| Form ID | Form Name | Deposit | Key Purpose |
|---------|-----------|---------|-------------|
| A | Notice of Change of Correspondence Address (Strata Roll) | None | Update mailing address on strata roll |
| B-1 | Application for Residential A&A (Renovation) | $1,000 | Renovation permit and contractor registration |
| B-2 | Contractor's Indemnity Form for A&A | None | Contractor liability undertaking (merged into B-1) |
| B-3 | Application for Permit for Contractor | None | Contractor access permit (merged into B-1) |
| C | Approval for A&A Work / House Removal | None | MA approval form (merged into B-1) |
| D-1 | Application for Moving In / Moving Out | $1,000 | Moving logistics and deposit |
| D-2 | Contractor's Indemnity Form for Moving In/Out | None | Mover liability undertaking (merged into D-1) |
| E | Request for Refund of Deposit (A&A / Moving) | None | Resident-initiated deposit refund request |
| F | Application for Residential Vehicle Registration | $50 | Register vehicle for carpark access |
| G | Application for Access Card | $50/card (fee) | Replacement or additional access cards |
| H | Application for Bicycle Tag | None | Bicycle parking tag |
| I | Application for Dining Pavilion Booking | $200 + fee | Reserve dining pavilion |
| J | Application for Function Room Booking | $200 + fee | Reserve function room |
| K | Request for Refund of Deposit (Facilities) | None | Facility deposit refund request |
| L | Registration of Residential Occupancy | None | Register occupants and tenancy details |

### 2.2 New Digital-Only Forms

Nine new forms have been identified that have no paper equivalent. These must be built from scratch in Hilife:

- Pet Registration
- Visitor Management System (VMS)
- Instructor/Coach Registration
- Carwash Bay Booking
- EV Lot Booking
- Temporary Overnight Parking Permit
- Visitor Parking
- Loading/Unloading Bay Request
- Bicycle Registration

---

## 3. E-Form Design

This section specifies the complete field requirements for each e-form. For existing Hilife drafts, the **Hilife Status** column indicates whether each field already exists, partially exists, is missing, or should be removed.

### Discrepancy Summary

| Form | Hilife ID | Current Qs | Required Fields | Missing | To Remove | Readiness |
|------|-----------|-----------|----------------|---------|-----------|-----------|
| A -- Address Change | 18237 | 4 | 5 | 2 | 1 | Near-complete |
| B-1 -- Renovation/A&A | 18271 | 8 | 20 | 9 | 3 | Major gaps |
| D-1 -- Moving In/Out | 18272 | 5 | 10 | 4 | 3 | Major gaps |
| E/K -- Refund of Deposit | 18273 | 5 | 0 | 0 | 0 | ELIMINATED |
| F -- Vehicle Registration | 18238 | 4 | 9 | 6 | 1 | Incomplete |
| G -- Access Card | 18274 | 3 | 6 | 4 | 2 | Major gaps |
| H -- Bicycle Tag | 18275 | 4 | 4 | 0 | 1 | Near-complete |
| I/J -- Dining / Function Room | N/A | N/A | N/A | N/A | N/A | Facility Booking |
| L -- Occupancy Registration | 18276 | 2 | 10 | 8 | 1 | Very sparse |
| Pet Registration | N/A | 0 | 8 | 8 | 0 | Not started |
| VMS | N/A | 0 | 7 | 7 | 0 | Not started |
| Instructor Registration | N/A | 0 | 7 | 7 | 0 | Not started |
| Completion & Inspection | N/A | 0 | 4 | 4 | 0 | Not started |

---

### 3.1 Form A -- Notice of Change of Correspondence Address

**Hilife E-Form ID: 18237 | Current: 4 questions | Required: 5 fields**

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | New Correspondence Address | Text (multi-line) | Yes | Exists | |
| 2 | Effective Date of Change | Date | Yes | Exists | |
| 3 | Contact Number | Text | Yes | MISSING | Mobile and/or home |
| 4 | Email Address | Text | No | MISSING | For correspondence |
| 5 | Consent (PDPA) | Single Choice (checkbox) | Yes | Exists | |
| - | ~~Official Use~~ | ~~Header~~ | Remove | Exists (remove) | MA uses approval workflow instead |

**Notes:** Near-complete. Add contact number and email fields, then remove the "Official Use" section. Verify entity name reads "MCST 4932". This is the closest form to being publish-ready and is recommended as a pilot.

---

### 3.2 Form B-1 -- Application for Residential A&A (Renovation) + Contractor Registration

**Hilife E-Form ID: 18271 | Current: 8 questions | Required: 20 fields**

Merged form combining paper Forms B-1, B-2, B-3, and C.

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| | **Section: Applicant Info** | | | | |
| 1 | Contact Number | Text | Yes | MISSING | Mobile |
| 2 | Email Address | Text | Yes | MISSING | |
| | **Section: Renovation Details** | | | | |
| 3 | Summary of Proposed Renovation Works | Text (multi-line) | Yes | MISSING | Description of scope |
| 4 | Date of Commencement | Date | Yes | MISSING | |
| 5 | Expected Date of Completion | Date | Yes | MISSING | |
| 6 | Drawing Plans / Renovation Proposal | Attachment | Yes | MISSING | Upload PDF/images |
| 7 | Hot Work Required? | Single Choice (Yes/No) | Yes | MISSING | If yes, hot work permit applies |
| | **Section: Contractor Info** | | | | |
| 8 | Name of Contractor Company | Text | Yes | Exists (QX) | Combined as Multiple Choice in Q1, needs restructuring |
| 9 | Contractor Business Reg. No. | Text | Yes | Exists (QX) | Combined in Q1, needs separate field |
| 10 | Contractor Address | Text | Yes | Exists (QX) | Combined in Q1, needs separate field |
| 11 | Contractor Person-in-Charge | Text | Yes | Exists (QX) | Combined in Q1, needs separate field |
| 12 | Contractor Contact Number | Text | Yes | Exists (QX) | Combined in Q1, needs separate field |
| 13 | Contractor Email | Text | Yes | MISSING | |
| 14 | Company Stamp | Attachment | Yes | Exists (Q3) | |
| | **Section: Worker Details** | | | | |
| 15 | Number of Workers | Number | Yes | MISSING | |
| 16 | Worker Names and ID Numbers | Text (multi-line) | Yes | MISSING | Name + work permit/passport no. Do NOT collect NRIC. |
| | **Section: Indemnity & Acknowledgment** | | | | |
| 17 | Contractor Indemnity Undertaking | Multiple Choice (checkboxes) | Yes | Exists (Q4) | Lift protection, common area clauses |
| 18 | Terms and Conditions Acknowledgment | Single Choice (checkbox) | Yes | Exists (Q2) | |
| 19 | PDPA Consent | Single Choice (checkbox) | Yes | Exists (Q2/Q4) | |
| 20 | Contractor Signature | Attachment | Yes | Exists (Q5) | |
| - | ~~NRIC Last 4 Digits~~ | ~~Text~~ | Remove | Exists (remove) | PDPA non-compliant by 31 Dec 2026 |
| - | ~~Official Use x2~~ | ~~Header~~ | Remove | Exists (Q6, Q8 -- remove) | MA uses approval workflow |
| - | ~~Deposit Cheque Number~~ | ~~Text~~ | Remove | N/A | Deposit collected via Facility Booking module |

**Notes:** Major gaps. The merge of B-1/B-2/B-3/C is correct in concept, but the form lacks renovation scope details, dates, worker list, and applicant contact info. The contractor info fields exist but are crammed into a single Multiple Choice question and need restructuring into separate text fields. NRIC field must be removed before publishing. Deposit collection is handled by Facility Booking module (Step 2 of the deposit workflow).

---

### 3.3 Form D-1 -- Application for Moving In / Moving Out

**Hilife E-Form ID: 18272 | Current: 5 questions | Required: 10 fields**

Merged form combining paper Forms D-1 and D-2.

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Moving Direction | Single Choice | Yes | MISSING | "Moving In" or "Moving Out" |
| 2 | Date of Moving | Date | Yes | Exists (Q1) | |
| 3 | Preferred Time Slot | Single Choice | Yes | MISSING | Morning (9am-1pm) / Afternoon (1pm-5pm) |
| | **Section: Contractor Info** | | | | |
| 4 | Name of Moving Company | Text | Yes | Partial (QX) | Combined in Q3, needs restructuring |
| 5 | Contractor Contact Number | Text | Yes | Partial (QX) | Combined in Q3 |
| 6 | Contractor Person-in-Charge | Text | Yes | MISSING | |
| 7 | Number of Workers | Number | No | MISSING | |
| | **Section: Indemnity & Acknowledgment** | | | | |
| 8 | Contractor Indemnity Undertaking | Multiple Choice (checkboxes) | Yes | Exists (Q4) | Lift protection, common area protection |
| 9 | Terms and Conditions Acknowledgment | Single Choice (checkbox) | Yes | Exists (Q3) | |
| 10 | PDPA Consent | Single Choice (checkbox) | Yes | Exists (Q3/Q4) | |
| - | ~~NRIC Last 4 Digits~~ | ~~Text~~ | Remove | Exists (Q4 -- remove) | PDPA non-compliant |
| - | ~~Deposit Cheque Number~~ | ~~Text~~ | Remove | Exists (Q2 -- remove) | Deposit via Facility Booking |
| - | ~~Official Use~~ | ~~Header~~ | Remove | Exists (Q5 -- remove) | |

**Notes:** Major gaps. Cannot distinguish moving in from moving out. Missing time slot preference. Cheque reference and NRIC field must be removed. Deposit collection is handled by Facility Booking module.

---

### 3.4 Form E/K -- Refund of Deposit -- ELIMINATED

**Hilife E-Form ID: 18273 (unpublished)**

This form is eliminated from the digital platform. The current Hilife draft (ID 18273) conflates two different refund processes and should be deleted.

**Rationale:** Under the proposed dual-module workflow, deposit refunds are no longer resident-initiated "requests." They are mandatory MA actions triggered at process closure:

- **A&A/Moving deposit refunds** -- MA processes via the Deposit Records page after inspection.
- **Facility booking deposit refunds** -- handled automatically by the Facility Booking module, or MA clicks Refund/Forfeit in Deposit Records.

The paper Forms E and K are replaced by the new "Completion & Inspection Request" e-form, which notifies the MA that work is complete and triggers inspection, rather than requesting a refund.

---

### 3.5 Form F -- Application for Residential Vehicle Registration

**Hilife E-Form ID: 18238 | Current: 4 questions | Required: 9 fields**

$50 refundable deposit is required for vehicle registration.

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Applicant Type | Single Choice | Yes | Exists (Q1) | "Subsidiary Proprietor" or "Tenant" |
| 2 | Vehicle Registration Plate No. | Text | Yes | MISSING | Exists in wrong form (18239) |
| 3 | Vehicle IU Number | Text | Yes | MISSING | Exists in wrong form (18239) |
| 4 | Vehicle Make and Model | Text | Yes | MISSING | Exists in wrong form (18239) |
| 5 | Vehicle Type | Single Choice | No | MISSING | Car / Motorcycle / Others |
| 6 | Company Vehicle Letter | Attachment | No | MISSING | Required if company-registered vehicle |
| 7 | Tenancy Agreement Copy | Attachment | No | MISSING | Required if tenant |
| 8 | Consent + Rules Acknowledgment | Multiple Choice (checkboxes) | Yes | Exists (Q3) | PDPA + carpark rules |
| 9 | Deposit Payment Confirmation | Attachment | Yes | MISSING | Upload PayNow screenshot ($50 to MCST 4932) |
| - | ~~Official Use~~ | ~~Header~~ | Remove | Exists (Q4 -- remove) | |

**Notes:** Incomplete. The critical vehicle details (plate, IU, make/model) are missing -- they exist in a separate form (ID 18239) and must be consolidated. $50 deposit collection is needed; since this is a refundable deposit, it follows the same deposit workflow concern as renovation/moving (credit card via Facility Booking or PayNow with screenshot upload).

---

### 3.6 Form G -- Application for Access Card

**Hilife E-Form ID: 18274 | Current: 3 questions | Required: 6 fields**

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Application Type | Single Choice | Yes | Exists (Q1) | "Replacement" or "Additional Card" |
| 2 | Number of Cards Required | Number | Yes | MISSING | |
| 3 | Card Holder Details | Text (multi-line) | Yes | MISSING | Name and relationship to SP per card |
| 4 | Reason for Replacement | Text | Conditional | MISSING | Required if "Replacement" |
| 5 | Payment Confirmation | Attachment | Yes | MISSING | Upload PayNow screenshot ($50/card) |
| 6 | PDPA Consent | Single Choice (checkbox) | Yes | Exists (Q2) | |
| - | ~~Cash/Cheque Reference~~ | ~~Text~~ | Remove | Exists (Q3 -- remove) | Payment via PayNow |
| - | ~~Official Use~~ | ~~Header~~ | Remove | Exists (Q3 -- remove) | |

**Notes:** Major gaps. Missing card holder details, quantity, and replacement reason. The $50/card fee should be collected via PayNow with screenshot upload as payment confirmation (see Section 4.1 special case).

---

### 3.7 Form H -- Application for Bicycle Tag

**Hilife E-Form ID: 18275 | Current: 4 questions | Required: 4 fields**

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Number of Bicycle Tags | Number | Yes | Exists (Q1) | |
| 2 | Application Type | Single Choice | Yes | Exists (Q2) | "First-time" or "Replacement" |
| 3 | Terms and Conditions Acknowledgment | Single Choice (checkbox) | Yes | Exists (Q3) | Bicycle parking rules |
| 4 | PDPA Consent | Single Choice (checkbox) | Yes | Exists (Q3) | |
| - | ~~Official Use~~ | ~~Header~~ | Remove | Exists (Q4 -- remove) | |

**Notes:** Near-complete. All required fields exist. Only action needed is removing the "Official Use" section and verifying entity name. Recommended as a pilot alongside Form A.

---

### 3.8 Forms I/J -- Dining Pavilion / Function Room Booking

**No e-form needed.** These are handled entirely by the Facility Booking module, which is already active and working.

- **Dining Pavilion** (Form I) -- $200 deposit + $25-50 booking fee, via Facility Booking.
- **Function Room** (Form J) -- $200 deposit + $100 booking fee, via Facility Booking.
- **Form K** (Refund Request for Facilities) -- eliminated. Refunds are automatic or MA-driven through Deposit Records.

---

### 3.9 Form L -- Registration of Residential Occupancy

**Hilife E-Form ID: 18276 | Current: 2 questions | Required: 10 fields**

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Registration Type | Single Choice | Yes | MISSING | "New Occupancy" or "Change of Occupancy" |
| 2 | Owner Name | Text | Yes | MISSING | Auto-populate from Hilife profile if possible |
| 3 | Tenancy Start Date | Date | Conditional | MISSING | Required if tenant |
| 4 | Tenancy End Date | Date | Conditional | MISSING | Required if tenant |
| 5 | Tenancy Agreement | Attachment | Conditional | MISSING | Required if tenant |
| 6 | Number of Occupants | Number | Yes | MISSING | Maximum 6 unrelated persons |
| 7 | Occupant Details | Text (multi-line) | Yes | Partial (QX) | Q1 "Tenant Info" -- very sparse, needs expansion |
| 8 | Emergency Contact Name | Text | Yes | MISSING | |
| 9 | Emergency Contact Number | Text | Yes | MISSING | |
| 10 | PDPA Consent | Single Choice (checkbox) | Yes | MISSING | |
| - | ~~Official Use~~ | ~~Header~~ | Remove | Exists (Q2 -- remove) | |

**Notes:** Very sparse. Only one actual resident-facing field exists (Q1 "Tenant Info"). The paper form collects significantly more detail. Eight fields must be added to bring this form to parity.

---

### 3.10 New: Pet Registration

**Not yet built in Hilife | Required: 8 fields**

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Pet Type | Single Choice | Yes | N/A | Dog / Cat / Others |
| 2 | Breed | Text | Yes | N/A | |
| 3 | Pet Name | Text | Yes | N/A | |
| 4 | Pet Photo | Attachment | Yes | N/A | For identification |
| 5 | AVS License Number | Text | Conditional | N/A | Required for dogs |
| 6 | Vaccination Certificate | Attachment | Yes | N/A | Up-to-date vaccination proof |
| 7 | Rules Acknowledgment | Single Choice (checkbox) | Yes | N/A | "I agree to abide by the pet rules and regulations" |
| 8 | PDPA Consent | Single Choice (checkbox) | Yes | N/A | |

---

### 3.11 New: Visitor Management System (VMS)

**Not yet built in Hilife | Required: 7 fields**

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Visitor Name | Text | Yes | N/A | |
| 2 | Visitor Contact Number | Text | No | N/A | |
| 3 | Visit Date | Date | Yes | N/A | |
| 4 | Expected Time of Arrival | Time | No | N/A | |
| 5 | Vehicle Number (if driving) | Text | No | N/A | For carpark access |
| 6 | Purpose of Visit | Single Choice | No | N/A | Social / Delivery / Service / Others |
| 7 | Number of Visitors | Number | No | N/A | Default 1 |

---

### 3.12 New: Instructor/Coach Registration

**Not yet built in Hilife | Required: 7 fields**

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Instructor/Coach Name | Text | Yes | N/A | |
| 2 | Contact Number | Text | Yes | N/A | |
| 3 | Activity/Sport | Single Choice | Yes | N/A | Swimming / Tennis / Gym / Yoga / Others |
| 4 | Schedule | Text (multi-line) | Yes | N/A | Days and times |
| 5 | Insurance/Certification Proof | Attachment | Yes | N/A | |
| 6 | Sponsoring Resident (Unit No.) | Text | Yes | N/A | Resident who engaged the coach |
| 7 | PDPA Consent | Single Choice (checkbox) | Yes | N/A | |

---

### 3.13 New: Completion & Inspection Request (Replaces Forms E and K)

**Not yet built in Hilife | Required: 4 fields**

This is a simple e-form submitted by residents when renovation or moving is complete, to trigger MA inspection and deposit refund.

| # | Field | Type | Required | Hilife Status | Notes |
|---|-------|------|----------|---------------|-------|
| 1 | Application Type | Single Choice | Yes | N/A | "Renovation Completed" or "Moving Completed" |
| 2 | Date of Completion | Date | Yes | N/A | |
| 3 | Remarks | Text (multi-line) | No | N/A | Any notes for MA |
| 4 | Acknowledgment | Single Choice (checkbox) | Yes | N/A | "I confirm all works are completed and common areas have been restored" |

---

### 3.14 Cross-Cutting Issues

The following issues affect multiple forms and must be resolved before any e-form is published:

- **NRIC last-4-digit collection must stop by 31 December 2026.** Affected forms: 18271 (Renovation), 18272 (Moving In/Out). Remove all NRIC fields and replace with alternative identification where necessary (e.g., passport or work permit number for foreign workers).

- **All "Official Use" sections should be removed from resident-facing e-forms.** These paper-era fields confuse residents. Use Hilife's built-in approval workflow (Pending/Approved/Rejected/Cancelled) and reply thread for MA processing notes instead.

- **Entity naming: replace "KINGSFORD HURAY DEVELOPMENT PTE LTD" with "MCST 4932."** The developer name is no longer applicable post-handover. All forms, notifications, and system references must use the correct MCST entity name.

- **Payment references: eliminate all cheque/cash references.** Use PayNow/Bank Transfer/Credit Card as the accepted payment modes. E-forms that currently reference cheques (18271, 18272, 18274) must be updated.

- **Price discrepancies between handbook and Hilife.** Tennis Court booking fee is $10 in the handbook but $10.90 in Hilife. Function Room booking fee shows as $100 in some contexts but $109 in Hilife. The approximately 9% Hilife surcharge likely covers platform and credit card processing fees. Pricing must be confirmed with the MCST council and aligned across all references.

---

## 4. Workflows

### 4.1 Non-Deposit Forms

Simple e-form submission and approval flow:

```
   Resident submits e-form
        |
        v
   MA receives notification and reviews
        |
   [Need more info?]
        |           \
       No           Yes --> MA posts in reply thread
        |                        |
        |                   Resident replies
        |                        |
        |           <------------+
        v
   MA approves or rejects
        |
        v
   Resident receives outcome notification
```

**Applies to:** Form A (Address Change), Form H (Bicycle Tag), Form L (Occupancy Registration), Pet Registration, VMS, Instructor/Coach Registration, Bicycle Registration.

Note: Forms that require fee or deposit collection use separate workflows -- see Section 4.2 (Fee Collection) and Section 4.3 (Deposit-Required).

---

### 4.2 Fee Collection Forms

For forms that require a non-refundable fee (not a deposit), the fee is collected via PayNow with proof of payment uploaded in the e-form.

```
   Resident submits e-form with application details
        |
        v
   MA reviews application
        |
   [Need more info?] --Yes--> MA uses reply thread --> Resident replies
        |
       No
        |
        v
   MA approves e-form
        |
        v
   MA replies with payment instruction:
   "Approved. Please pay $XX via PayNow to MCST 4932
    and upload the payment screenshot."
        |
        v
   Resident pays via PayNow
   Uploads payment screenshot in e-form reply thread
        |
        v
   MA verifies payment
   Processes the request (issues card, decal, etc.)
```

**Applies to:**
- Access Card (Form G) -- $50 per card (non-refundable)

**Why not use Facility Booking?** Booking fees in Facility Booking are per-slot, not per-quantity. An Access Card application may request 3 cards ($150) which cannot be easily handled in a single booking slot. PayNow with screenshot is simpler and more flexible for variable amounts.

---

### 4.3 Deposit-Required Forms

**The problem:** Hilife e-forms cannot collect deposits or fees. The Facility Booking module can collect deposits via credit card hold but does not support rich application forms with contractor details, signatures, and back-and-forth communication.

**Proposed 3-step flow:**

```
STEP 1: E-FORM APPLICATION
   Resident submits e-form with full details
        |
        v
   MA reviews application
        |
   [Need more info?] --Yes--> MA uses reply thread --> Resident replies
        |
       No
        |
        v
   MA approves e-form
        |
        v
STEP 2: DEPOSIT COLLECTION (Facility Booking Module)
   MA instructs resident via reply thread:
   "Application approved. Please proceed to Facility Booking
    to pay the $1,000 deposit."
        |
        v
   Resident opens Facility Booking module
   Selects "Renovation Deposit" or "Moving Deposit" category
   Pays $1,000 via credit card hold
        |
        v
   Deposit status = "In Use"
   Work/move may commence
        |
        v
STEP 3: COMPLETION AND REFUND
   Resident submits "Completion & Inspection Request" e-form
   (or notifies MA via reply thread)
        |
        v
   MA inspects common areas
        |
   [Damage found?]
        |
       No --> MA clicks "Refund" in Deposit Records --> $1,000 returned
        |
       Yes --> MA clicks "Forfeit" in Deposit Records --> Full/partial deduction
```

**Applies to:**
- Renovation (A&A) -- Form B-1 equivalent, $1,000 deposit
- Moving In/Out -- Form D-1 equivalent, $1,000 deposit
- Vehicle Registration -- Form F equivalent, $50 deposit (smaller amount, PayNow may be simpler)

**Forms eliminated:** Form E (Refund of A&A Deposit) and Form K (Refund of Facility Deposit). Refund is now an MA-driven action at process closure, not a resident request.

#### Concern: Credit Card Processing Fees

Hilife adds an approximately 9% surcharge on credit card transactions:

| Item | Handbook Price | Hilife Price | Markup |
|------|---------------|-------------|--------|
| Tennis Court booking fee | $10.00/hr | $10.90/hr | +9% |
| Function Room booking fee | $100/session | $109/session | +9% |

On a deposit charge-and-refund cycle, the MCST may lose 2-3% in credit card processing fees (processors typically do not return the merchant fee on refunds):

| Deposit Amount | Estimated Processing Fee (2-3%) | Net Cost to MCST |
|---------------|-------------------------------|-------------------|
| $1,000 (Renovation/Moving) | $20 - $30 | $20 - $30 per cycle |
| $200 (Function Room/Dining) | $4 - $6 | $4 - $6 per cycle |

**Estimated annual impact:**

| Category | Volume | Cost per Cycle | Annual Cost |
|----------|--------|---------------|-------------|
| Renovation/Moving deposits ($1,000) | ~50 | $20 - $30 | $1,000 - $1,500 |
| Facility deposits ($200) | ~200 | $4 - $6 | $800 - $1,200 |
| **Total** | | | **$1,800 - $2,700** |

**Questions to clarify with Hilife:**

1. Is there a per-transaction fee on deposit charges and refunds, and what is the exact rate?
2. Does the ~9% surcharge apply to deposits, or only to booking fees?
3. On full refund, does the resident receive 100% of the original deposit?
4. Does the MCST absorb the credit card processing fee on both charge and refund?
5. What happens when a deposit reaches its 6-month expiry -- auto-refund, flag for MA, or extend?
6. Are PayNow or bank transfer available as alternative deposit modes?

#### Alternative: PayNow for High-Value Deposits

If credit card processing costs are confirmed to be material, the $1,000 deposits can be collected via PayNow instead:

1. Resident submits e-form application (as normal).
2. Upon approval, MA instructs resident to pay $1,000 via PayNow to the MCST bank account.
3. Resident uploads payment confirmation screenshot in the e-form reply thread.
4. MA verifies payment and creates a manual deposit record in Hilife Deposit Records.
5. On completion, MA processes refund via bank transfer.

This avoids credit card fees entirely but adds manual steps for both the resident and the MA. **Recommendation:** Confirm exact fee structure with Hilife first, then decide. If fees are negligible, use the credit card flow for simplicity. If fees are material ($20-30 per cycle), use PayNow for the $1,000 deposits while keeping credit card for the smaller $200 facility deposits.

---

### 4.4 Facility Bookings

The Facility Booking module is already working for Function Rooms, Dining Pavilions, and Tennis Court.

```
   Resident selects facility and time slot
        |
        v
   System collects booking fee (non-refundable)
   System places deposit hold on credit card (if applicable)
        |
        v
   MA approves booking (if approval required)
        |
        v
   Event occurs
        |
        v
   [Damage?]
       No --> Auto-refund deposit (or MA clicks Refund)
       Yes --> MA clicks Forfeit
```

**Forms replaced:**
- Form I (Dining Pavilion Booking) -- replaced by Facility Booking module
- Form J (Function Room Booking) -- replaced by Facility Booking module
- Form K (Refund Request) -- eliminated (auto-refund or MA-driven)

**New facility categories to create:**
- Carwash Bay (pricing TBD)
- EV Lot (pricing TBD)
- Temporary Overnight Parking (pricing TBD)

**Current deposit amounts:**

| Facility | Deposit | Booking Fee |
|----------|---------|-------------|
| Function Room | $200 | $100/session |
| Dining Pavilion | $200 | $25-50/session |
| Tennis Court | $0 | $10/hr |

**Improvements needed:**
- Align pricing between handbook and Hilife configuration (resolve the ~9% discrepancy)
- Enable booking Q&A (`enable_qa`) for categories where additional info is needed (e.g., guest count for function rooms)
- Configure cancellation windows for new categories
- Determine whether Visitor Parking and Loading/Unloading Bay should be facility bookings or e-forms

---

## 5. Action Items

### 5.1 Immediate (Before Publishing Any E-Forms)

| # | Action | Affected |
|---|--------|----------|
| 1 | Remove all NRIC collection fields | 18271, 18272 |
| 2 | Remove all "Official Use" sections | All e-forms |
| 3 | Replace "KINGSFORD HURAY DEVELOPMENT PTE LTD" with "MCST 4932" | All forms |
| 4 | Remove all cheque/cash references; update to PayNow/Bank Transfer/Credit Card | 18271, 18272, 18273, 18274 |
| 5 | Clarify credit card processing fees with Hilife (per-transaction costs, surcharge on deposits, 6-month expiry behaviour, refund handling) | All deposit workflows |
| 6 | Confirm pricing with MCST council (Tennis $10 vs $10.90, Function Room $100 vs $109) | Facility categories |

### 5.2 E-Form Completion

| # | Action | E-Form ID | Details |
|---|--------|-----------|---------|
| 7 | Add contact number and email to Address Change | 18237 | 2 fields to add, 1 to remove |
| 8 | Add renovation scope, dates, worker list, applicant contact to A&A form | 18271 | 9 fields to add, 3 to remove; restructure Q1 into separate fields |
| 9 | Add moving direction, time slot, contractor PIC to Moving form | 18272 | 4 fields to add, 3 to remove |
| 10 | Add vehicle plate, IU, make/model, vehicle type, document uploads to Vehicle Registration | 18238 | 5 fields to add (consolidate from 18239), 1 to remove |
| 11 | Add card holder details, quantity, replacement reason, payment upload to Access Card | 18274 | 4 fields to add, 2 to remove |
| 12 | Expand Occupancy Registration with occupant details, tenancy period, emergency contact, consent | 18276 | 8 fields to add, 1 to remove |
| 13 | Delete the Refund Request e-form | 18273 | Eliminated by proposed workflow |

### 5.3 Facility Booking Configuration

| # | Action | Details |
|---|--------|---------|
| 14 | Reactivate "Renovation Deposit" facility category | deposit_switch=1, deposit=$1,000, enable_qa=0, booking_fee=$0 |
| 15 | Reactivate "Moving Deposit" facility category | deposit_switch=1, deposit=$1,000, enable_qa=0, booking_fee=$0 |
| 16 | Create "Carwash Bay" facility category | Pricing and rules TBD |
| 17 | Create "EV Lot" facility category | Pricing and rules TBD |
| 18 | Create "Temporary Overnight Parking" facility category | Pricing and rules TBD |
| 19 | Enable booking Q&A for Function Room and Dining Pavilion | Guest count, event type |
| 20 | Determine approach for Visitor Parking and Loading/Unloading Bay | Facility Booking vs E-form vs VMS integration |

### 5.4 New E-Forms to Build

| # | Form Name | Fields | Complexity |
|---|-----------|--------|------------|
| 21 | Pet Registration | 8 | Low |
| 22 | Visitor Management System (VMS) | 7 | Medium |
| 23 | Instructor/Coach Registration | 7 | Medium |
| 24 | Completion & Inspection Request | 4 | Low |

### 5.5 Testing & Rollout

| # | Action | Details |
|---|--------|---------|
| 25 | Publish Form A (Address Change) as pilot | Lowest risk, near-complete |
| 26 | Publish Form H (Bicycle Tag) as second pilot | Also near-complete |
| 27 | Test full 3-step deposit workflow end-to-end | E-form submission, Facility Booking deposit, inspection, refund/forfeit |
| 28 | Publish remaining e-forms in batches | Non-deposit forms first, then deposit forms |
| 29 | Communicate to residents | Provide guide on digital submission process |
| 30 | Decommission paper forms | After digital equivalents are stable |
