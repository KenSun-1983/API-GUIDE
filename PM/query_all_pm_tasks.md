# Query All PM Tasks

## API Information
Query all PM task information

## API Path
`http://XX.XX.XX.XX:60040/pmManagement/api/pmmng/history_task`

## Request Protocol
HTTP

## Request Method
GET

## Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `page` | Page number | No | `number` | | 1 |
| `start` | Starting row number | No | `number` | | 0 |
| `limit` | Maximum number of rows returned each time | No | `number` | | 100 |

## Request Body
None

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `total` | Total number of records | Yes | `number` | | | 1 |
| `data` | Task data list | Yes | `array` | | | `[{"taskId":1,"neId":12382,...}]` |
| `data>>item[0]` | Task item | Yes | `object` | | | |
| `data>>item[0]>>taskId` | Task ID | Yes | `number` | | | 1 |
| `data>>item[0]>>neId` | NE ID | Yes | `number` | | | 12382 |
| `data>>item[0]>>neIp` | NE IP address | Yes | `string` | | | "132.232.12.29" |
| `data>>item[0]>>neName` | NE Name | Yes | `string` | | | "iTN8600-城西 9" |
| `data>>item[0]>>neTypeId` | NE Type ID | Yes | `number` | | | 21002 |
| `data>>item[0]>>fixedNetypeId` | Fixed NE Type ID | Yes | `number` | | | 21002 |
| `data>>item[0]>>neTypeName` | NE Type Name | Yes | `string` | | | "iTN8600-A" |
| `data>>item[0]>>collectType` | Collection type | Yes | `number` | | | 0 |
| `data>>item[0]>>taskType` | Task type | Yes | `number` | | | 1 |
| `data>>item[0]>>taskStatus` | Task status | Yes | `number` | | | 1 |
| `data>>item[0]>>collectPeriod` | Collection period | Yes | `number` | | | 2 |
| `data>>item[0]>>executeTime` | Execute time | No | `null` | | | null |
| `data>>item[0]>>endTime` | End time | No | `null` | | | null |
| `data>>item[0]>>metricTmplId` | Metric template ID | No | `null` | | | null |
| `data>>item[0]>>protocolType` | Protocol type | No | `null` | | | null |
| `data>>item[0]>>collectTimeType` | Collection time type | Yes | `number` | | | 1 |
| `data>>item[0]>>monthPlanEnable` | Monthly plan enable | No | `null` | | | null |
| `data>>item[0]>>scheduleRule` | Schedule rule | No | `null` | | | null |
| `data>>item[0]>>weekPlanEnable` | Weekly plan enable | No | `null` | | | null |
| `data>>item[0]>>collectLastingWay` | Collection lasting way | No | `null` | | | null |
| `data>>item[0]>>pmVer` | PM version | Yes | `string` | | | "0" |
| `data>>item[0]>>createTime` | Create time | Yes | `number` | | Unix timestamp (ms) | 1720504173821 |
| `data>>item[0]>>createUser` | Create user | Yes | `string` | | | "neAdd" |
| `data>>item[0]>>modifyTime` | Modify time | No | `null` | | | null |
| `data>>item[0]>>modifyUser` | Modify user | No | `null` | | | null |
| `data>>item[0]>>neState` | NE state | Yes | `number` | | | 1 |
| `data>>item[0]>>startEndTime` | Start-end time | No | `null` | | | null |
| `data>>item[0]>>dailyStartTime` | Daily start time | No | `null` | | | null |
| `data>>item[0]>>dailyEndTime` | Daily end time | No | `null` | | | null |
| `errorMsg` | Error message | No | `null` | | | null |

### Success Example
```json
{
    "data": [
        {
            "taskId": 1,
            "neId": 12382,
            "neIp": "132.232.12.29",
            "neName": "iTN8600-城西 9",
            "neTypeId": 21002,
            "fixedNetypeId": 21002,
            "neTypeName": "iTN8600-A",
            "collectType": 0,
            "taskType": 1,
            "taskStatus": 1,
            "collectPeriod": 2,
            "executeTime": null,
            "endTime": null,
            "metricTmplId": null,
            "protocolType": null,
            "collectTimeType": 1,
            "monthPlanEnable": null,
            "scheduleRule": null,
            "weekPlanEnable": null,
            "collectLastingWay": null,
            "pmVer": "0",
            "createTime": 1720504173821,
            "createUser": "neAdd",
            "modifyTime": null,
            "modifyUser": null,
            "neState": 1,
            "startEndTime": null,
            "dailyStartTime": null,
            "dailyEndTime": null
        }
    ],
    "total": 1,
    "errorMsg": null
}
```
