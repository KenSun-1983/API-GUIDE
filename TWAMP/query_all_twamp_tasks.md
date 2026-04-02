# Query All TWAMP Tasks

## API Information
Query and return all TWAMP task information

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
| `page` | Page number | No | `number` | | 1 |
| `start` | Starting row number | No | `number` | | 0 |
| `limit` | Maximum number of rows returned each time | No | `number` | | 15 |

### Request Example
```json
{
    "page": 1,
    "start": 0,
    "limit": 15
}
```

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `total` | Total number of records | Yes | `number` | | | 1 |
| `data` | Task information list | No | `array` | | | `[{"createTime":"2023-12-27 10:51:46",...}]` |
| `data>>item[0]` | Task item | | `object` | | | |
| `data>>item[0]>>createTime` | Task creation time | | `string` | | | "2023-12-27 10:51:46" |
| `data>>item[0]>>createUser` | User who created the task | | `string` | | | "administrator" |
| `data>>item[0]>>destNeLabel` | Destination network element name | | `string` | | | "172.16.67.185" |
| `data>>item[0]>>destNetypeId` | Destination NE type ID | | `number` | | | 2012 |
| `data>>item[0]>>destSeriesId` | Destination series ID | | `number` | | | 1 |
| `data>>item[0]>>e2eServiceId` | Task ID (used in other query interfaces) | | `number` | | | 2 |
| `data>>item[0]>>e2eServiceUrl` | Task URL (used in other query interfaces) | | `string` | | | "/e2e_service_id=518136620204921" |
| `data>>item[0]>>gmtCreate` | Creation timestamp | | `string` | | | "2023-12-27 10:51:46" |
| `data>>item[0]>>gmtModified` | Modification timestamp | | `string` | | | "2023-12-27 11:25:15" |
| `data>>item[0]>>isDeployed` | Deployment status | | `number` | | | 1 |
| `data>>item[0]>>measureStartTime` | Measurement start time | | `string` | | | "2023-12-27 10:51:58" |
| `data>>item[0]>>measureStatus` | Measurement status | | `number` | 1 = Start | | 1 |
| `data>>item[0]>>operateStatus` | Operation status | | `number` | 6 = Operation successful | | 6 |
| `data>>item[0]>>resultDes` | Result description | | `string` | | | "" |
| `data>>item[0]>>serviceName` | Task name | | `string` | | | "A" |
| `data>>item[0]>>serviceType` | Service type | | `number` | | | 1 |
| `data>>item[0]>>srcNeLabel` | Source network element name | | `string` | | | "172.16.67.119" |
| `data>>item[0]>>srcNetypeId` | Source NE type ID | | `number` | | | 2007 |
| `data>>item[0]>>srcSeriesId` | Source series ID | | `number` | | | 1 |
| `data>>item[0]>>templateId` | Template ID | | `number` | | | -1 |
| `code` | Response code | | `number` | | | 0 |

### Success Example
```json
{
    "total": 1,
    "data": [
        {
            "createTime": "2023-12-27 10:51:46",
            "createUser": "administrator",
            "destNeLabel": "172.16.67.185",
            "destNetypeId": 2012,
            "destSeriesId": 1,
            "e2eServiceId": 2,
            "e2eServiceUrl": "/e2e_service_id=518136620204921",
            "gmtCreate": "2023-12-27 10:51:46",
            "gmtModified": "2023-12-27 11:25:15",
            "isDeployed": 1,
            "measureStartTime": "2023-12-27 10:51:58",
            "measureStatus": 1,
            "operateStatus": 6,
            "resultDes": "",
            "serviceName": "A",
            "serviceType": 1,
            "srcNeLabel": "172.16.67.119",
            "srcNetypeId": 2007,
            "srcSeriesId": 1,
            "templateId": -1
        }
    ],
    "code": 0
}
```

## Usage Notes
1. **e2eServiceId**: This field is crucial as it's used in other query interfaces to get detailed task information and performance data
2. **e2eServiceUrl**: Used together with e2eServiceId for detailed queries
3. **measureStatus**: 1 indicates the measurement has started
4. **operateStatus**: 6 indicates the operation was successful
