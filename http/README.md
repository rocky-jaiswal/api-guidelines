# HTTP

## Use standard HTTP codes

### Success Codes

Code	Meaning	Methods
200
OK - this is the standard success response
All

201
Created - Returned on successful entity creation. You are free to return either an empty response or the created resource in conjunction with the Location header. (More details found in the Common Headers.) Always set the Location header.
POST, PUT

202
Accepted - The request was successful and will be processed asynchronously.
POST, PUT, DELETE, PATCH

204
No content - There is no response body
PUT, DELETE, PATCH

207
Multi-Status - The response body contains multiple status informations for different parts of a batch/bulk request. See Must: Use Code 207 for Batch or Bulk Requests.
POST

### Redirection Codes

Code	Meaning	Methods

301
Moved Permanently - This and all future requests should be directed to the given URI.
All

303
See Other - The response to the request can be found under another URI using a GET method.
PATCH, POST, PUT, DELETE

304
Not Modified - resource has not been modified since the date or version passed via request headers If-Modified-Since or If-None-Match.
GET

### Client Side Error Codes

Code	Meaning	Methods

400
Bad request - generic / unknown error. Should also be delivered in case of input payload fails business logic validation.
All

401
Unauthorized - the users must log in (this often means "Unauthenticated")
All

403
Forbidden - the user is not authorized to use this resource
All

404
Not found - the resource is not found
All

405
Method Not Allowed - the method is not supported, see OPTIONS
All

406
Not Acceptable - resource can only generate content not acceptable according to the Accept headers sent in the request
All

408
Request timeout - the server times out waiting for the resource
All

409
Conflict - request cannot be completed due to conflict, e.g. when two clients try to create the same resource or if there are concurrent, conflicting updates
POST, PUT, DELETE, PATCH

410
Gone - resource does not exist any longer, e.g. when accessing a resource that has intentionally been deleted
All

412
Precondition Failed - returned for conditional requests, e.g. If-Match if the condition failed. Used for optimistic locking.
PUT, DELETE, PATCH

415
Unsupported Media Type - e.g. clients sends request body without content type
POST, PUT, DELETE, PATCH

423
Locked - Pessimistic locking, e.g. processing states
PUT, DELETE, PATCH

428
Precondition Required - server requires the request to be conditional (e.g. to make sure that the "lost update problem" is avoided).
All

429
Too many requests - the client does not consider rate limiting and sent too many requests. See Must: Use Code 429 with Headers for Rate Limits.
All

### Server Side Error Codes:

Code	Meaning	Methods

500
Internal Server Error - a generic error indication for an unexpected server execution problem (here, client retry may be sensible)
All

501
Not Implemented - server cannot fulfill the request (usually implies future availability, e.g. new feature).
All

503
Service Unavailable - service is (temporarily) not available (e.g. if a required component or downstream service is not available) — client retry may be sensible. If possible, the service should indicate how long the client should wait by setting the 'Retry-After' header.
All
