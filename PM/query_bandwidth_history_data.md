# Query Bandwidth History Data

## API Information
Query the bandwidth value of the device within a certain period of time.

## API Path
`http://XX.XX.XX.XX:60040/pmManagement/api/pmmng/collectdata/historydata`

## Request Protocol
HTTP

## Request Method
PATCH

## Query Parameters
None

## Request Body
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `startTime` | Start time | Yes | `number` | Unix timestamp (ms) | 1722930599000 |
| `endTime` | End time | Yes | `number` | Unix timestamp (ms) | 1723024199214 |
| `createTime` | Create time | No | `number` | Unix timestamp (ms) | 1722911455396 |
| `metricGroupList` | Metric group list | Yes | `array` | | `[{"metricGroupId":"130",...}]` |
| `metricGroupList>>item[0]` | Metric group item | Yes | `object` | | |
| `metricGroupList>>item[0]>>metricGroupId` | Metric group ID | Yes | `string` | | "130" |
| `metricGroupList>>item[0]>>baseGroupId` | Base group ID | Yes | `string` | | "130" |
| `metricGroupList>>item[0]>>metricGroupName` | Metric group name | Yes | `string` | | "Business Traffic(Port+VLAN)" |
| `metricGroupList>>item[0]>>metricPairIdList` | Metric pair ID list | Yes | `array` | | `["206"]` |
| `metricGroupList>>item[0]>>detailIdList` | Detail ID list | Yes | `array` | | `["1"]` |

### Request Example
```json
{
    "startTime": 1722930599000,
    "endTime": 1723024199214,
    "createTime": 1722911455396,
    "metricGroupList": [
        {
            "metricGroupId": "130",
            "baseGroupId": "130",
            "metricGroupName": "Business Traffic(Port+VLAN)",
            "metricPairIdList": ["206"],
            "detailIdList": ["1"]
        }
    ]
}
```

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `msg` | Message body containing history data | Yes | `object` | | | See example below |

### Response Example (msg content)
```json
{
    "206": {
        "/ne=8124628/port=4/vlan=100/cos=8": {
            "InOctets": {
                "1722996902000": {
                    "time": "1722996902000",
                    "/ne=8124628/port=4/vlan=100/cos=8": "0.0"
                }
            },
            "InGreenOctets": {
                "1722996902000": {
                    "time": "1722996902000",
                    "/ne=8124628/port=4/vlan=100/cos=8": "0.0"
                }
            },
            "InYellowOctets": {
                "1722996902000": {
                    "time": "1722996902000",
                    "/ne=8124628/port=4/vlan=100/cos=8": "0.0"
                }
            },
            "InRedOctets": {
                "1722996902000": {
                    "time": "1722996902000",
                    "/ne=8124628/port=4/vlan=100/cos=8": "0.0"
                }
            }
        }
    },
    "207": {
        "/ne=8124628/port=4/vlan=100/cos=8": {
            "OutOctets": {
                "1722996902000": {
                    "time": "1722996902000",
                    "/ne=8124628/port=4/vlan=100/cos=8": "0.0"
                }
            },
            "OutGreenOctets": {
                "1722996902000": {
                    "time": "1722996902000",
                    "/ne=8124628/port=4/vlan=100/cos=8": "0.0"
                }
            },
            "OutYellowOctets": {
                "1722996902000": {
                    "time": "1722996902000",
                    "/ne=8124628/port=4/vlan=100/cos=8": "0.0"
                }
            },
            "OutRedOctets": {
                "1722996902000": {
                    "time": "1722996902000",
                    "/ne=8124628/port=4/vlan=100/cos=8": "0.0"
                }
            }
        }
    }
}
```

## Usage Notes
1. **Time Format**: All timestamps are in milliseconds (Unix epoch time)
2. **Response Structure**: The response is organized by metric pair ID (e.g., "206", "207")
3. **Resource Path**: Each metric contains data keyed by resource path (e.g., "/ne=8124628/port=4/vlan=100/cos=8")
4. **Metric Types**: Within each resource, data is further divided by metric type (e.g., "InOctets", "OutOctets")
5. **Time-series Data**: Each metric contains multiple time points with their corresponding values
