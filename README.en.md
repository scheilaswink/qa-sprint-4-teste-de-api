🇧🇷 [Português](README.md) | 🇺🇸 English

# API testing — product kits and delivery

Sprint 4 project from the TripleTen QA Engineer program: manual REST API testing with **Postman**, with positive and negative test cases for two endpoints and bug reports in Jira.

## Goal

Check whether two API endpoints follow the business rules in the documentation and correctly handle valid, invalid, empty and missing data.

## Endpoints tested

1. **`POST /api/v1/kits/:id/products`** — adds products to a kit.
   Tests with valid and invalid kit and product IDs (string, empty, null, special characters, negative number, very long value), empty `productsList` or sent as an object, `quantity` with invalid types, missing request body and the 30-items-per-kit limit.
2. **`POST /order-and-go/v1/delivery`** — calculates delivery for the "Order and Go" service.
   Boundary value tests for delivery time (`deliveryTime`), quantity (`productsCount`) and weight (`productsWeight`), delivery cost, and fields with invalid types, empty or missing.

## Results

| Endpoint | Test cases | Passed | Failed |
|---|---|---|---|
| `POST /api/v1/kits/:id/products` | 26 | 7 | 19 |
| `POST /order-and-go/v1/delivery` | 41 | 19 | 22 |
| **Total** | **67** | **26** | **41** |

Each failed case generated a bug report in Jira (SPRINT04-1 to SPRINT04-41).

### Examples of bugs found

- The API returns **500 Internal Server Error** instead of **400 Bad Request** when it receives an ID or `quantity` with an invalid type.
- The API accepts with **200 OK** requests with no body, an empty `productsList` or a negative `quantity`.
- The delivery endpoint accepts negative or zero `productsCount` and `productsWeight`.
- The delivery endpoint returns `"isItPossibleToDeliver": true` outside the allowed hours (`deliveryTime` 7 and 23).
- The delivery cost (`clientDeliveryCost`) is calculated incorrectly at some quantity and weight boundaries.

## Files

- [`casos-de-teste-api.xlsx`](casos-de-teste-api.xlsx): spreadsheet with one tab per endpoint (in Portuguese). Each case has a title, steps, test data (request body), expected result, actual result, status and a link to the bug.
- [`BUGS.md`](BUGS.md): the 41 bug reports copied from Jira (in Portuguese), with the cURL command for each request, expected result and actual result.

## What I learned

- **HTTP:** methods, status codes (200, 400, 404, 405, 500) and the structure of requests and responses.
- **API testing:** creating positive and negative cases from the documentation, using equivalence partitioning and boundary values.
- **Postman:** sending requests, building JSON request bodies and checking responses.
- **API bug reports:** including the endpoint in the title, the full cURL command, the expected result and the actual result.
