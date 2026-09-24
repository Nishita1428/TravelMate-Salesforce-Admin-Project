# Validation Rules

After creating the Lead fields and formula fields, I added validation rules to make sure incorrect travel enquiry details cannot be saved.

The rules cover travel dates, traveller counts, budget, passport information and basic travel details.

## Validation Rules

| Rule | Purpose |
|---|---|
| Departure Date Cannot Be Past | Prevents a past departure date |
| Return Date Cannot Be Before Departure | Makes sure the return date is not before the departure date |
| At Least One Adult Required | Requires at least one adult traveller |
| Adults and Children Cannot Be Negative | Prevents negative traveller counts |
| Estimated Budget Must Be Positive | Allows blank budget but does not allow zero or negative values |
| International Enquiry Requires Passport | Requires passport confirmation for international package enquiries |
| Origin and Destination Cannot Be Same | Prevents the same city from being entered as both origin and destination |
| Travel Information Required | Requires origin, destination and departure date when an enquiry type is selected |

## Testing

I tested the rules using both valid and invalid values.

Some of the cases I tested:

- Past departure date → blocked
- Return date before departure date → blocked
- Zero adults or no adults → blocked
- Negative traveller count → blocked
- Zero or negative budget → blocked
- International enquiry without passport confirmation → blocked
- Same origin and destination → blocked
- Missing travel information → blocked

I also tested valid values to make sure genuine enquiries could still be saved.

## Example

For an international enquiry:

- Enquiry Type: International Package
- Origin City: Delhi
- Destination: Dubai
- Departure Date: Future date
- Passport Available: Checked

The record was saved successfully after passing the validation checks.
