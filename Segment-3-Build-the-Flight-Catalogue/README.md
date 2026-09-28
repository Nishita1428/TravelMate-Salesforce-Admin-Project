# Segment 3 – Build the Flight Catalogue

## What I worked on

In this segment, I built the internal flight catalogue for TravelMate.

The goal was to create a structured way to maintain airline information, airport details, and scheduled flights before any future API integration.

I created custom objects, lookup relationships, formula fields, and validation rules to keep the flight data consistent and realistic.

---

## Objects Created

### 1. Airline

The Airline object stores basic airline master information.

Fields created:

- Airline Code – Text (3), Unique
- Airline Name – Text (80)
- Airline Status – Picklist
  - Active
  - Inactive

---

### 2. Airport

The Airport object stores airport master information.

Fields created:

- Airport Code – Text (3), Unique
- Airport Name – Text (80)
- Airport City – Text (80)
- Airport Country – Text (80)
- International Airport – Checkbox

---

### 3. Scheduled Flight

The Scheduled Flight object stores individual flight schedules.

Fields created:

- Flight Number – Text (10)
- Airline – Lookup to Airline
- Origin Airport – Lookup to Airport
- Destination Airport – Lookup to Airport
- Departure Date/Time – Date/Time
- Arrival Date/Time – Date/Time
- Travel Class – Picklist
  - Economy
  - Premium Economy
  - Business
  - First
- Available Seats – Number (3,0)
- Base Fare – Currency
- Taxes and Fees – Currency
- Total Fare – Formula (Currency)
- Flight Duration Hours – Formula (Number)
- Route Display – Formula (Text)
- Flight Availability – Formula (Text)

---

## Object Relationships

The Scheduled Flight object is connected to:

- Airline through a Lookup relationship
- Airport through an Origin Airport Lookup
- Airport through a Destination Airport Lookup

This allows multiple scheduled flights to use the same airline and airport records.

---

## Formula Fields

### Total Fare

Calculates the total flight fare by adding the base fare and taxes/fees.

```text
Base Fare + Taxes and Fees
