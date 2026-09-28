
# Segment 5 — Integrated Booking-Readiness Challenge

## Overview

Segment 5 brings together the TravelMate configuration created across Segments 1–4 into one end-to-end booking-readiness process.

The objective is to verify that the complete TravelMate data model, relationships, formulas and validation rules work together for a realistic travel enquiry and quotation journey.

This segment focuses on configuration verification and end-to-end testing before any future booking automation or API integration.

---

## Business Requirement

TravelMate requires a controlled manual process before future development begins.

The complete configuration must be verified through an end-to-end travel journey covering:

- Customer enquiry
- Lead routing
- Travel package
- Package itinerary
- Airline and airport data
- Scheduled flights
- Travel quotation
- Quotation flights
- Quotation calculations
- Validation rules

---

## TravelMate Application

A Lightning App named **Travel Mate** was created containing the required objects:

- Leads
- Travel Packages
- Package Itineraries
- Airlines
- Airports
- Scheduled Flights
- Quotation Flights
- Travel Quotations

---

## Complete Data Model

The final TravelMate data model connects the configuration created in the previous segments.

### Lead

Captures the original customer travel enquiry.

### Travel Package

Stores reusable travel package information such as destination, dates, pricing and traveller limits.

### Package Itinerary

Stores the day-wise activities belonging to a Travel Package.

### Airline

Stores airline master data.

### Airport

Stores airport master data including airport code, city and country.

### Scheduled Flight

Stores available flight schedules and connects an airline with origin and destination airports.

### Travel Quotation

Stores the customer-specific quotation and connects the original Lead with the selected package.

### Quotation Flight

Stores the individual scheduled flights selected for a quotation.

---

## End-to-End Relationship

The overall TravelMate process follows this structure:

```text
Customer Enquiry
      ↓
     Lead
      ↓
Lead Assignment Rule
      ↓
Travel Package + Package Itinerary
      +
Airline + Airport + Scheduled Flight
      ↓
Travel Quotation
      ↓
Quotation Flight
      ↓
Package + Flight Charges
      ↓
Discount
      ↓
Final Quotation Amount
