# Segment 2 – Build the Travel Package Catalogue

## What I worked on

In this segment, I built a reusable travel package catalogue for TravelMate.

The purpose was to maintain travel packages along with their day-wise itinerary details. I used Custom Objects, Master-Detail Relationship, Formula Fields, Roll-Up Summary and Validation Rules to keep the package data organized and consistent.

---

## Custom Objects

### 1. Travel Package

The Travel Package object stores the main details of a travel package.

Fields created:

- Package Number – Auto Number
- Package Name – Text
- Package Type – Picklist
  - Domestic
  - International
- Destination City – Text
- Destination Country – Text
- Start Date – Date
- End Date – Date
- Base Price Per Adult – Currency
- Base Price Per Child – Currency
- Maximum Travellers – Number
- Status – Picklist
  - Draft
  - Active
  - Inactive
- Package Duration – Formula
- Total Itinerary Cost – Roll-Up Summary
- Package Cost Indicator – Formula

---

### 2. Package Itinerary

The Package Itinerary object stores the day-wise activities included in a travel package.

Fields created:

- Itinerary Name – Text
- Day Number – Number
- Activity Name – Text
- Activity Type – Picklist
  - Travel
  - Hotel
  - Sightseeing
  - Meal
  - Leisure
- Activity Date – Date
- Activity Cost – Currency
- Included – Checkbox

---

## Master-Detail Relationship

I created a Master-Detail relationship between:

**Travel Package → Package Itinerary**

Travel Package acts as the parent record, while Package Itinerary acts as the child record.

This allows one travel package to contain multiple itinerary records.

