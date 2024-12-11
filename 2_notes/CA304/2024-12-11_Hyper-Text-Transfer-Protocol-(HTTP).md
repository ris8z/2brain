---
date: 2024-12-11 
tags: 
    - CA304
hubs: 
    -   "[[2024-12-07_Network-2|network 2]]"
---

# Hyper Text Transfer Protocol (HTTP)

## **HTTP Response Codes**
- **1xx - Informational:** Temporary responses.
  - `100`: Continue, `101`: Switching protocols, `102`: Processing, `103`: Early hints.
- **2xx - Success:** Request succeeded.
  - `200`: OK, `202`: Accepted, `204`: No content.
- **3xx - Redirection:** Resource moved or cached.
  - `301`: Moved permanently, `304`: Not modified, `305`: Use proxy.
- **4xx - Client Error:** Issues with the request.
  - `400`: Bad request, `401`: Unauthorized, `403`: Forbidden, `404`: Not found.
- **5xx - Server Error:** Issues on the server side.
  - `500`: Internal server error, `501`: Not implemented, `502`: Bad gateway, `503`: Service unavailable.

## **HTTP Request/Response Structure**
1. **Start-line:** Describes the request or response status.
2. **Headers:** Provide metadata for the request/response.
3. **Blank line:** Indicates meta-information is complete.
4. **Optional body:** Contains associated data (e.g., form content).

## **HTTPS**
- **HTTP with encryption and verification.**
- Uses **TLS/SSL** to:
  - Encrypt HTTP requests/responses.
  - Digitally sign them for security.
