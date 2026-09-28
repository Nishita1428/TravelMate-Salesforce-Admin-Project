# Segment 4 — Customer Travel Quotation

## Overview

In this segment, I built a Travel Quotation system for TravelMate to allow travel consultants to prepare customer quotations based on selected travel packages and scheduled flights.

A quotation can be:

- Package Only
- Flight Only
- Package + Flight

The quotation calculates traveller counts, package charges, flight charges, gross amount, discount and final quotation amount.

---

## Business Requirement

After reviewing a customer enquiry, a travel consultant prepares a quotation.

The quotation can include a travel package, scheduled flights, or both. The system calculates the applicable package and flight charges and maintains the quotation status and validity date.

---

## Objects Created

### 1. Travel Quotation

Parent object used to store the customer's quotation.

**Record Name:** Auto Number — `QT-{0000}`

Key fields:

- Quotation Type
- Customer Enquiry
- Selected Package
- Adults
- Children
- Total Travellers
- Adult Package Charge
- Child Package Charge
- Total Package Charge
- Total Flight Charge
- Number of Flights
- Gross Quotation Amount
- Discount Percentage
- Discount Amount
- Final Quotation Amount
- Quotation Status
- Valid Until

---

### 2. Quotation Flight

Child object used to store the individual flight lines included in a quotation.

**Record Name:** Auto Number — `QF-{0000}`

Fields:

- Flight Direction
- Scheduled Flight
- Passenger Count
- Fare Per Passenger
- Flight Line Total

---

## Relationships

### Travel Quotation → Lead

A Lookup relationship connects the quotation with the original customer enquiry.

### Travel Quotation → Travel Package

A Lookup relationship connects the quotation with the selected travel package.

### Travel Quotation → Quotation Flight

A Master-Detail relationship is used because quotation flight records belong to a specific quotation.

One quotation can contain multiple flight lines, such as:

- Outbound flight
- Return flight

### Quotation Flight → Scheduled Flight

A Lookup relationship connects each quotation flight line with a scheduled flight from the flight catalogue.

---

## Formula Fields

### Total Travellers

Calculates the total number of travellers.

```text
Adults + Children
