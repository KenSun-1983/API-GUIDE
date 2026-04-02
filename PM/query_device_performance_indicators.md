# Query Device Performance Indicators

## API Information
From all NE performance collection task information, query the specific NE we want to query based on the NE name, and fill in the `fixedNetypeId`, `taskId`, and `metricTmplId` from the returned information into the corresponding parameters of this interface.

## API Path
`http://XX.XX.XX.XX:60040/pmManagement/api/pmmng/history_task/oneShowNew`

## Request Protocol
HTTP

## Request Method
GET

## Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `fixedNetypeId` | Fixed NE Type ID | Yes | `number` | From query all PM tasks API | 21002 |
| `taskId` | Task ID | Yes | `number` | From query all PM tasks API | 1 |
| `tmpId` | Template ID | Yes | `number` | From query all PM tasks API | |

## Request Body
None

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `data` | Performance indicator data list | Yes | `array` | | | `[{"metricGroupId":130,...}]` |
| `data>>item[0]` | Metric group item | Yes | `object` | | | |
| `data>>item[0]>>metricGroupId` | Metric group ID | Yes | `number` | | | 130 |
| `data>>item[0]>>baseGroupId` | Base group ID | Yes | `number` | | | 130 |
| `data>>item[0]>>metricGroupName` | Metric group name | Yes | `string` | | | "Business Traffic(Port+VLAN)" |
| `data>>item[0]>>tempId` | Template ID | Yes | `number` | | | 3 |
| `data>>item[0]>>rsUrlList` | Resource URL list | Yes | `array` | | | `[{"detailId":1,...}]` |
| `data>>item[0]>>rsUrlList>>item[0]` | Resource URL item | Yes | `object` | | | |
| `data>>item[0]>>rsUrlList>>item[0]>>detailId` | Detail ID | Yes | `number` | | | 1 |
| `data>>item[0]>>rsUrlList>>item[0]>>taskId` | Task ID | Yes | `number` | | | 26 |
| `data>>item[0]>>rsUrlList>>item[0]>>uuid` | UUID | Yes | `string` | | | "2560c015b3a74558" |
| `data>>item[0]>>rsUrlList>>item[0]>>rsUrl` | Resource URL | Yes | `string` | | | "/ne=8124628/port=4/vlan=100/cos=8" |
| `data>>item[0]>>rsUrlList>>item[0]>>neId` | NE ID | Yes | `number` | | | 8124628 |
| `data>>item[0]>>rsUrlList>>item[0]>>rsIndex` | Resource index | Yes | `string` | | | "4.100.8" |
| `data>>item[0]>>rsUrlList>>item[0]>>rsType` | Resource type | Yes | `string` | | | "port vlan cos pm" |
| `data>>item[0]>>rsUrlList>>item[0]>>rsName` | Resource name | Yes | `string` | | | "a" |
| `data>>item[0]>>rsUrlList>>item[0]>>metricGroupId` | Metric group ID | Yes | `number` | | | 130 |
| `data>>item[0]>>rsUrlList>>item[0]>>throsholdTmplId` | Threshold template ID | Yes | `number` | | | 1 |
| `data>>item[0]>>rsUrlList>>item[0]>>throsholdTmplName` | Threshold template name | Yes | `string` | | | "a" |
| `data>>item[0]>>rsUrlList>>item[0]>>oidVer` | OID version | Yes | `number` | | | 0 |
| `data>>item[0]>>rsUrlList>>item[0]>>calculateConstantOne` | Calculate constant one | No | `null` | | | null |
| `data>>item[0]>>rsUrlList>>item[0]>>calculateConstantTwo` | Calculate constant two | No | `null` | | | null |
| `data>>item[0]>>rsUrlList>>item[0]>>orderIndex` | Order index | No | `null` | | | null |
| `data>>item[0]>>rsUrlList>>item[0]>>neName` | NE name | Yes | `string` | | | "172.16.67.114" |
| `data>>item[0]>>rsUrlList>>item[0]>>neIp` | NE IP | No | `null` | | | null |
| `data>>item[0]>>metricPairDetailList` | Metric pair detail list | Yes | `array` | | | `[{"metricPairId":206,...}]` |
| `data>>item[0]>>metricPairDetailList>>item[0]` | Metric pair detail item | Yes | `object` | | | |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricPairId` | Metric pair ID | Yes | `number` | | | 206 |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricPairName` | Metric pair name | Yes | `string` | | | "In Octets" |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricUnit` | Metric unit | Yes | `string` | | | "bytes" |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricPairLabel` | Metric pair label | No | `null` | | | null |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricBaseList` | Base metric list | Yes | `array` | | | `[{"metricId":518,...}]` |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricBaseList>>item[0]` | Base metric item | Yes | `object` | | | |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricBaseList>>item[0]>>metricId` | Metric ID | Yes | `number` | | | 518 |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricBaseList>>item[0]>>metricName` | Metric name | Yes | `string` | | | "In Octets" |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricBaseList>>item[0]>>metricLabel` | Metric label | Yes | `string` | | | "InOctets" |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricBaseList>>item[0]>>metricUnit` | Metric unit | Yes | `string` | | | "bytes" |
| `data>>item[0]>>metricPairDetailList>>item[0]>>metricBaseList>>item[0]>>baseValue` | Base value | No | `null` | | | null |
| `total` | Total number of records | Yes | `number` | | | 1 |
| `errorMsg` | Error message | No | `null` | | | null |

### Success Example
```json
{
    "data": [
        {
            "metricGroupId": 130,
            "baseGroupId": 130,
            "metricGroupName": "Business Traffic(Port+VLAN)",
            "tempId": 3,
            "rsUrlList": [
                {
                    "detailId": 1,
                    "taskId": 26,
                    "uuid": "2560c015b3a74558",
                    "rsUrl": "/ne=8124628/port=4/vlan=100/cos=8",
                    "neId": 8124628,
                    "rsIndex": "4.100.8",
                    "rsType": "port vlan cos pm",
                    "rsName": "a",
                    "metricGroupId": 130,
                    "throsholdTmplId": 1,
                    "throsholdTmplName": "a",
                    "oidVer": 0,
                    "calculateConstantOne": null,
                    "calculateConstantTwo": null,
                    "orderIndex": null,
                    "neName": "172.16.67.114",
                    "neIp": null
                }
            ],
            "metricPairDetailList": [
                {
                    "metricPairId": 206,
                    "metricPairName": "In Octets",
                    "metricUnit": "bytes",
                    "metricPairLabel": null,
                    "metricBaseList": [
                        {
                            "metricId": 518,
                            "metricName": "In Octets",
                            "metricLabel": "InOctets",
                            "metricUnit": "bytes",
                            "baseValue": null
                        },
                        {
                            "metricId": 519,
                            "metricName": "In Green Octets",
                            "metricLabel": "InGreenOctets",
                            "metricUnit": "bytes",
                            "baseValue": null
                        },
                        {
                            "metricId": 520,
                            "metricName": "In Yellow Octets",
                            "metricLabel": "InYellowOctets",
                            "metricUnit": "bytes",
                            "baseValue": null
                        },
                        {
                            "metricId": 521,
                            "metricName": "In Red Octets",
                            "metricLabel": "InRedOctets",
                            "metricUnit": "bytes",
                            "baseValue": null
                        }
                    ]
                },
                {
                    "metricPairId": 207,
                    "metricPairName": "Out Octets",
                    "metricUnit": "bytes",
                    "metricPairLabel": null,
                    "metricBaseList": [
                        {
                            "metricId": 522,
                            "metricName": "Out Octets",
                            "metricLabel": "OutOctets",
                            "metricUnit": "bytes",
                            "baseValue": null
                        },
                        {
                            "metricId": 523,
                            "metricName": "Out Green Octets",
                            "metricLabel": "OutGreenOctets",
                            "metricUnit": "bytes",
                            "baseValue": null
                        },
                        {
                            "metricId": 524,
                            "metricName": "Out Yellow Octets",
                            "metricLabel": "OutYellowOctets",
                            "metricUnit": "bytes",
                            "baseValue": null
                        },
                        {
                            "metricId": 525,
                            "metricName": "Out Red Octets",
                            "metricLabel": "OutRedOctets",
                            "metricUnit": "bytes",
                            "baseValue": null
                        }
                    ]
                }
            ]
        }
    ],
    "total": 1,
    "errorMsg": null
}
```
