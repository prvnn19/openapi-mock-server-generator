# Use-Case Flow Specification

## Use Case: Generate and Test Mock API Endpoint

### Primary Actor
API Developer / QA Engineer

### Goal
Generate a working mock REST endpoint from an OpenAPI 3.0 specification and obtain a schema-compliant response.

### Preconditions
1. The OpenAPI Mock Server Generator is running.
2. The user has a valid OpenAPI 3.0 YAML or JSON specification.
3. The specification contains at least one API endpoint.
4. The user has permission to upload and execute the specification.

### Postconditions

#### Success
- The OpenAPI specification has been parsed successfully.
- Mock endpoints have been generated.
- The requested endpoint returns a JSON response.
- The response conforms to the defined schema.
- Configured response latency is applied.

#### Failure
- The invalid specification/request is rejected.
- An appropriate error response is returned.
- The server remains operational.

### Main Success Scenario
1. The API Developer uploads an OpenAPI 3.0 YAML/JSON specification.
2. The system validates the uploaded file format.
3. The system parses the OpenAPI specification.
4. The system extracts API paths, HTTP methods, parameters, and response schemas.
5. The system generates corresponding mock REST endpoints.
6. The user configures the desired simulated response latency.
7. The API Developer or QA Engineer sends a request to a generated mock endpoint.
8. The system validates the incoming request against the OpenAPI definition.
9. The system generates randomized JSON data based on the response schema.
10. The system validates the generated response against the schema.
11. The system applies the configured response latency.
12. The system sends the JSON response to the client.
13. The user verifies the response and API behavior.

### Alternate Flow — Invalid API Request
1. The system detects that the incoming request does not conform to the OpenAPI specification.
2. The system identifies the validation failure.
3. The request is rejected.
4. The system returns an appropriate HTTP error response.
5. The invalid request is logged for debugging/testing purposes.
6. The mock server remains available for subsequent requests.
