# Overall Introduction

RCView adopts a B/S (Browser/Server) architecture. All interfaces have corresponding REST API endpoints on the backend, allowing users to retrieve resource information, query alarm information, and push configurations by calling these APIs.

For security reasons, REST API access is not enabled by default in RCView. REST APIs can only be used after being enabled through backend configuration.

## User Guide

1. **Authentication**: Authenticate yourself first to obtain an access token.
   View getToken interface documentation.[getToken](getToken.md)
2. **Making Requests with Token**: Send requests using appropriate HTTP methods.
   For all HTTP requests，Must add the token data obtained from [getToken](getToken.md) to the Authentication-Token in the HTTP header, for example:
   ```http
   GET /api/v1/resource HTTP/1.1
   Host: example.com
   Content-Type: application/json
   Authentication-Token:WyIwIiwiY2M2NDA1MTVkYmE5ZTQ5NDEyZGIyYmVkNThkNWJhMGUiXQ.DTivLg.hK1nnOeqWu9BUeY6apcfwSq2u6g
   ```
4. **Handling Responses**: Handle responses according to the returned status codes and data formats.	
