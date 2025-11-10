# Overall Introduction

RCView adopts a B/S (Browser/Server) architecture. All interfaces have corresponding REST API endpoints on the backend, allowing users to retrieve resource information, query alarm information, and push configurations by calling these APIs.

For security reasons, REST API access is not enabled by default in RCView. REST APIs can only be used after being enabled through backend configuration.

## Enabling REST API Functionality

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
## User Guide

1. **Authentication**: Authenticate yourself first to obtain an access token.
2. **Making Requests**: Send requests using appropriate HTTP methods.
3. **Handling Responses**: Handle responses according to the returned status codes and data formats.
