# Segment 1 – Capture and Route Travel Enquiries

## What I worked on

In this segment, I started building the lead management part of the TravelMate Salesforce application.

The requirement was to capture travel enquiry details such as the type of enquiry, destination, travel dates, number of travellers and estimated budget.

I used the standard Salesforce Lead object and added custom fields according to the project requirements.

## Lead Fields Added

### Basic Information

- Enquiry Type – Picklist
- Origin City – Text
- Destination – Text
- Departure Date – Date
- Return Date – Date
- Adults – Number
- Children – Number
- Estimated Budget – Currency
- Passport Available – Checkbox

### Formula Fields

- Total Travellers
- Travel Duration
- Enquiry Priority

## Formula Logic

### Total Travellers

Total Travellers is calculated using the number of adults and children.

`Adults + Children`

For example, if there are 2 adults and 1 child, the total traveller count is 3.

### Travel Duration

Travel duration is calculated using the departure and return dates.

`Return Date - Departure Date + 1`

The `+1` is used because both the departure and return dates are included in the travel duration.

### Enquiry Priority

The enquiry priority is calculated from the estimated budget:

- ₹2,00,000 or above → Hot
- ₹75,000 to below ₹2,00,000 → Warm
- Below ₹75,000 → Standard
- Blank budget → Blank

## Testing

I created test Lead records to verify that the formula fields were calculating the expected values.

For example:

- 2 Adults + 1 Child → 3 Total Travellers
- 10 Oct to 14 Oct → 5 Days
- ₹2,00,000 Budget → Hot Priority

## Salesforce Concepts Practiced

- Custom Fields
- Picklist
- Number and Currency Fields
- Checkbox
- Formula Fields
- Formula Return Types
- Basic Lead Data Management


## Lead Queues

I created three Lead queues to separate travel enquiries based on the type of enquiry.

### Queues Created

- Domestic Package Queue
- International Package Queue
- Flight Queue

All three queues are configured to work with the Lead object.

These queues will be used with the Lead Assignment Rule to route new enquiries to the appropriate team.

### Queue Setup

![Lead Queues](./Screenshot/lead-queues.png)

