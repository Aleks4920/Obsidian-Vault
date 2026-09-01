---
tags: [work, orbital, form, form-io, mobile]
notion_source: "https://www.notion.so/319fe6aa14b980a8877ed4a0519b2def"
status: "Done"
last_synced: "2026-04-12"
---

# Orbital Hardware Request Form

Rebuilding the Supply Request Form from GoCanvas into Form.io for the Orbital Mobile App. Used by field technicians to request supplies from the warehouse. Must be mobile-first, clean, simple, and controlled. See also [[tasks]] and [[git]].

## Overview

**Platform:** Form.io inside Orbital Mobile App
**Users:** Field technicians
**Purpose:** Request supplies from warehouse

### Submission Routing

Upon submission, send email to:
- qc@orbitalcustoms.com
- shipping@orbitalcustoms.com

## Form Requirements

### Header Section

| Field | Type | Notes |
|---|---|---|
| Name | Text | Required; auto-fill from logged-in user if possible |
| Date | Date | Required; default today |
| Time | Time | Required; default current time |
| Needed By | Date | Required; date supplies must arrive by |
| Shipping Address Confirmation | Radio | Required: "Ship to Home of Record" or "Ship to Different Address" |

If "Ship to Different Address" is selected, display a required multiline address field.

### Priority & Shipping Control

- **Priority** (Dropdown, Required): Normal / Urgent
  - If Urgent: show required "Reason for Urgent Request" field
- **Shipping Method** (Dropdown, Required): Standard / Overnight
  - If Overnight: show required "Who approved overnight shipping?" (approver name)

### Supply Items

- Radio-style quantity selectors, default 0, horizontal segmented-button layout
- Grouped in collapsible panels
- Sections:
  - Zip Ties
  - Standard Connectors
  - Tape / Hardware / Loom
  - Fuses ATC and MINI
  - Wire and Relays
  - Heat Shrink Connectors
  - OE Pins Splicepack

### Notes

Optional multiline "Notes / Special Requests" field.

### Non-Ship Warning (Display Only)

> We do not ship the below items — purchase and turn in receipt to payroll:
> - 3M VHB double-side tape
> - Silicone

## Validation Rules

- Name, Date, Time, Needed By, Priority, Shipping Method all required
- If Urgent → Reason required
- If Overnight → Approver required
- If Ship to Different Address → Address required
- At least one supply item must have quantity > 0

## Email Format

**Subject:** `Supply Request – {Name} – Needed By {NeededBy}`

**Body includes:** Name, Date, Time, Needed By, Shipping Method, Priority, conditional fields (Reason / Approver if applicable), shipping destination, non-zero items only, Notes if provided.

## Post-Submission

Show confirmation summary:
- Requested items
- Shipping method
- Needed by date
- Timestamp

Message: "Your supply request has been submitted."

## Request History

Inside Orbital Mobile App: "My Supply Requests" view showing:
- Submission date
- Needed by date
- Status
- Ability to view past requests tied to logged-in user

## Acceptance Criteria

- [ ] Form renders properly in mobile
- [ ] All validation rules function correctly
- [ ] Email notification verified
- [ ] Urgent + Overnight logic enforced
- [ ] Address confirmation required
- [ ] Non-zero item validation working
- [ ] Submission summary visible
- [ ] History view functional
