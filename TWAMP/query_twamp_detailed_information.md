# Query TWAMP Task Detailed Information

## API Information
Query and return detailed information of a TWAMP task

## API Path
`http://XX.XX.XX.XX/measure_sla_north/measure_sla_config/v1/twamp/e2e_service_information`

## Request Protocol
HTTP

## Request Method
PUT

## Query Parameters
None

## Request Body
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `serviceType` | Service type | No | `number` | Fixed as 1 | 1 |
| `e2eServiceUrl` | E2E service URL | Yes | `string` | From query all tasks API | "/e2e_service_id=518136620204921" |
| `templateId` | Template ID | No | `number` | Fixed as -1 | -1 |

### Request Example
```json
{
    "serviceType": 1,
    "e2eServiceUrl": "/e2e_service_id=518136620204921",
    "templateId": -1
}
```

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `total` | Total number of records | Yes | `number` | | | 1 |
| `data` | Task detailed information | Yes | `object` | | | See example below |
| `data>>createUser` | User who created the task | Yes | `string` | | | "administrator" |
| `data>>destIp` | Destination IP address | Yes | `string` | | | "10.1.2.185" |
| `data>>destNeId` | Destination NE ID | Yes | `number` | | | 31 |
| `data>>destNeLabel` | Destination network element name | Yes | `string` | | | "172.16.67.185" |
| `data>>destNeTypeId` | Destination NE type ID | Yes | `number` | | | 2012 |
| `data>>destUdpPort` | Destination UDP port | Yes | `number` | | | 862 |
| `data>>operateStatus` | Operation status | Yes | `number` | 6 = Operation successful | | 6 |
| `data>>serviceName` | Service name | Yes | `string` | | | "A" |
| `data>>serviceType` | Service type | Yes | `number` | | | 1 |
| `data>>srcIp` | Source IP address | Yes | `string` | | | "10.1.2.119" |
| `data>>srcNeId` | Source NE ID | Yes | `number` | | | 28 |
| `data>>srcNeLabel` | Source network element name | Yes | `string` | | | "172.16.67.119" |
| `data>>srcNeTypeId` | Source NE type ID | Yes | `number` | | | 2007 |
| `data>>svlan` | Service VLAN ID | Yes | `number` | | | 1000 |
| `code` | Response code | Yes | `number` | | | 0 |

### Success Example
```json
{
    "total": 1,
    "data": {
        "createUser": "administrator",
        "destIp": "10.1.2.185",
        "destNeId": 31,
        "destNeLabel": "172.16.67.185",
        "destNeTypeId": 2012,
        "destUdpPort": 862,
        "operateStatus": 6,
        "serviceName": "A",
        "serviceType": 1,
        "srcIp": "10.1.2.119",
        "srcNeId": 28,
        "srcNeLabel": "172.16.67.119",
        "srcNeTypeId": 2007,
        "svlan": 1000
    },
    "code": 0
}
```

## Usage Notes
1. **Prerequisite**: You must first call the "Query All TWAMP Tasks" API to get the `e2eServiceUrl`
2. **Fixed Values**: 
   - `serviceType` should be fixed as 1
   - `templateId` should be fixed as -1
3. **Key Information Returned**:
   - Source and destination IP addresses
   - Source and destination NE information
   - UDP port for TWAMP testing (typically 862)
   - Service VLAN configuration

## Related APIs
- [Query All TWAMP Tasks](query_all_twamp_tasks.md) - Get the list of all TWAMP tasks
- [Query TWAMP Task Performance Information](query_twamp_task_performance_information.md) - Get performance metrics
