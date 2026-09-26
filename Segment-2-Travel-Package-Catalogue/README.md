# Segment 2 – Build the Travel Package Catalogue

## What I worked on

In this segment, I built a reusable travel package catalogue for TravelMate.

The setup allows a travel package to store its basic details, pricing, validity dates and capacity, while multiple itinerary records can be maintained under each package.

I also used Salesforce relationships, formula fields, roll-up summaries and validation rules to keep the package data consistent.

## Custom Objects

### Travel Package

The Travel Package object stores the main package information, including:

- Package Name
- Package Type
- Destination City
- Destination Country
- Start Date
- End Date
- Base Price Per Adult
- Base Price Per Child
- Maximum Travellers
- Status
- Package Duration
- Total Itinerary Cost
- Package Cost Indicator

### Package Itinerary

The Package Itinerary object stores day-wise activities for each travel package.

Fields include:

- Day Number
- Activity Name
- Activity Type
- Activity Date
- Activity Cost
- Included

## Master-Detail Relationship

I created a Master-Detail relationship between Travel Package and Package Itinerary.

Travel Package acts as the parent record and Package Itinerary acts as the child record.

This allows one travel package to contain multiple itinerary records.

## Formula Fields

### Package Duration

Calculates the inclusive number of days between the package Start Date and End Date.

```text
End Date - Start Date + 1
