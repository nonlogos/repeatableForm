# Add Service Form Spec Doc

## Summary

The purpose of this document is to cover the topic of what it takes to build the Add Service Form

## Basic Requirements

- Needs to allow users to submit new service information for their market
- Needs to allow user to identify the market they want to add services to 
- Needs to include default fields that should always exist with prefilled info
- Needs to allow user to add service and service-specific fields
- Needs to allow user to repeatly add service and repeatly add service fields
- Needs to export form data into CSV file upon form submisson

## Tech Requirements

- Angular 2
- ngCsv

## Behavioral guide
User should be able to select their market from dropdown. Then enter in as many new services and service-specific fields per service as they need. When they click on submit button, a CSV file populated with form data should be generated and downloaded to user machine.

### Methodology

The Add Service Form will include these fields

- Market (dropdown with prepopulated available markets)[R]
_ ** repeatable field group
- New Service (text)[R]
- Alternate Label (Read Only - text)
- Date and Time (Read Only- Date and Time)
- Event Location (Read Only - text)
- Note from Concierge (Read Only - text Area)
  ** Repeatable field group
- Custom field name (text)
- Custom field type (dropdown with propopulated available data types)

#### Process

1. The form should be hosted on app.key.co and check to make sure user is authenticated to use the form
2. User should enter all the required fields on the form
3. There should be buttons (Add more) for each repeatable area:
	- The entire New Service field group
	- Custom feild field group within New Service
4. User should hit submit
5. Upon form submission, a CSV file populated with form data should be generated and downloaded to user machine.

#### constructing the folio object

The following array is constructed from form data to generate their equivalent CSV file with Market info as part of the header.

```
[	
	{Service: "Tast of San Francisco"},
	{Item Fields: "Alternate Label"},
	{Item Type: "Text"},
	{Item Fields: "Date and Time"},
	{Item Type: "Date and Time"},
	{Item Fields: "Event Location"},
	{Item Type: "Text"},
	{Service: "Farmer's Market + Private Chef"},
	{Item Fields: "Alternate Label"},
	{Item Type: "Text"},
	{Item Fields: "Date and Time"},
	{Item Type: "Date and Time"},
	{Item Fields: "Event Location"},
	{Item Type: "Text"}
]

```
#### Future possible addition
- Instead of downloading the CSV, how to send the CSV as an attachment to an email?



 