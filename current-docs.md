Overview
Authentication
Once you have been issued an API key, authentication must be made on each request using an X-Api-Key header:

curl -H 'X-Api-Key: %YourApiKey%' 'https://www.daysoftheyear.com/api/v2/'
Caching
We recommend caching responses locally. Values refresh every 1 hour. Results are sorted by our internal editorial grading values, and then by type (day > month > other).

Endpoints
/today/
Returns events for today’s date.

curl -H 'X-Api-Key: %YourApiKey%' 'https://www.daysoftheyear.com/api/v2/today/'
/date/yyyy/mm/
Returns events for a specific month.

curl -H 'X-Api-Key: %YourApiKey%' 'https://www.daysoftheyear.com/api/v2/date/2022/01/'
/date/yyyy/mm/dd/
Returns events for a specific date (day).

curl -H 'X-Api-Key: %YourApiKey%' 'https://www.daysoftheyear.com/api/v2/date/2022/01/23/'
Query Parameters
limit (int)
Limit the number of results returned.

timezone_offset (int)
Offset the request from the UTC server default. Values must be between -12 and 12.

Response
The response format of each endpoints are identical; all responses are supplied in JSON format with the following data:

code – HTTP Response code of the Days Of The Year server
meta (array)
cache_status (string) – If you are receiving a cached response.
response_count (int) – The count of events returned for the date requested.
request_type (string) – DATE or TODAY, based on endpoint.
data (array) – An array of objects, each containing:
name (string) – Name of event.
url (string) – Event URL.
excerpt (string) – First 50 words of content or bespoke summary.
type (string) – Type of event; day, week or month.