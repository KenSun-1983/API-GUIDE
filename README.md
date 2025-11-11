# API Documentation Homepage

Welcome to our API documentation! This API provides a series of interfaces for developers to use. 

# Overall Introduction

RCView adopts a B/S (Browser/Server) architecture. All interfaces have corresponding REST API endpoints on the backend, allowing users to retrieve resource information, query alarm information, and push configurations by calling these APIs.

For security reasons, REST API access is not enabled by default in RCView. REST APIs can only be used after being enabled through backend configuration.

## Step 1:Enabling REST API Functionality

Log in to the server where RCView is installed and navigate to /comp/service/webapp/config/default.json in the installation directory.

In the file, locate the following section:
```json
{
  "north": {
    "/couchdb": "127.0.0.1:5984",
    "/cloudvpn": "127.0.0.1:60150",
    "/alarm_north": "127.0.0.1:60030",
    "/measure_sla_north": "127.0.0.1:61304"
  }
}
```
Add the specific content that needs to be added for the API to this section, For the specific content that needs to be added, please refer to the specific API interface documentation.
```json
{
  "north": {
    "/couchdb": "127.0.0.1:5984",
    "/cloudvpn": "127.0.0.1:60150",
    "/alarm_north": "127.0.0.1:60030",
    "/tiap_ems_north": "127.0.0.1:61308",
    "/measure_sla_north": "127.0.0.1:61304"
  }
}
```
Then restart the web app module.
```bash
npm restart www
```
## Step 2:Use REST API

1. **Authentication**

   Authenticate yourself first to obtain an access token.View getToken interface documentation.[getToken](getToken.md)

   **Note:** `The validity period of the token is 15 minutes by default. After expiration, the API will prompt a verification failure, and a new token will need to be requested.`
   
3. **Making Requests with Token**
   
   Send requests using appropriate HTTP methods.For all HTTP requests，Must add the token data obtained from [getToken](getToken.md) to the Authentication-Token in the HTTP header, for example:

   ```http
   GET /api/v1/resource HTTP/1.1
   Host: example.com
   Content-Type: application/json
   Authentication-Token:WyIwIiwiY2M2NDA1MTVkYmE5ZTQ5NDEyZGIyYmVkNThkNWJhMGUiXQ.DTivLg.hK1nnOeqWu9BUeY6apcfwSq2u6g
   ```
5. **Handling Responses**
   Parse the returned data according to the specific API documentation.

## API Index
- [Token API](getToken.md)
- [LLDP API](/EMS/lldp.md)

Please click the links above for more information.

## Video Example



https://github.com/user-attachments/assets/9dfdb205-fcf8-4ea1-ad12-a26cb1e82b40

