## API Information
Query performance data. Through this API, you can obtain performance - related information based on specified parameters.

### Detailed Explanation
***Open API Interface***
Log in to the server where RCView is installed and navigate to /comp/service/webapp/config/default.json in the installation directory.
In the file, locate the following section and add "/tiap_wdm_north":"127.0.0.1:61600".

In the current version, the string "tiap_wdm_north" can be specified arbitrarily, but it cannot be the same as any existing string. If you use another string, simply use your defined string in the API Path.

```json
"north": {
            "/couchdb": "127.0.0.1:5984",
            "/cloudvpn": "127.0.0.1:60150",
            "/alarm_north":"127.0.0.1:60030",
            "/tiap_wdm_north":"127.0.0.1:61600",
            "/measure_sla_north":"127.0.0.1:61304"
        }
```

### API Path
`https://172.16.61.51/tiap_wdm_north/tiap_ems_wdm_mgt/v1/performanceQuery/query_performance`

### Request Protocol
HTTP

### Request Method
POST

## Request Body
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `neId` | The ID of the network element | Yes | `number` |  | 404 |
| `fixedNetypeId` | The fixed network type ID | Yes | `number` |  | 20002 |
| `metricDetailList` | A list of metric pair IDs | Yes | `array` |  | `[{"metricPairId":107},{"metricPairId":109},{"metricPairId":110}]` |
| `metricDetailList>>item[0]>>metricPairId` | The ID of a metric pair | Yes | `number` |  | 107 |
| `cardId` | The ID of the card | Yes | `string` |  | `/ne=404/shelf=1/slot=1/card=1.1` |

## Request Body Example
```json
{"neId":404,"fixedNetypeId":20002,"metricDetailList":[{"metricPairId":107},{"metricPairId":109},{"metricPairId":110}],"cardId":"/ne=404/shelf=1/slot=1/card=1.1"}
```

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `total` | The total number of performance data items | Yes | `number` |  |  | 8 |
| `data` | The performance data list | Yes | `array` |  |  |  |
| `data>>item` | The performance data item | Yes | `object` |  |  |  |
| `data>>item>>avg` | The average value of the metric (if applicable) | No | `string` |  |  | "0.0" |
| `data>>item>>collectTime` | The collection time of the metric | Yes | `string` |  |  | "2025-11-12 18:00:02" |
| `data>>item>>id` | The ID of the performance data record | Yes | `number` |  |  | 144 |
| `data>>item>>max` | The maximum value of the metric (if applicable) | No | `string` |  |  | "0.0" |
| `data>>item>>metricName` | The name of the metric | Yes | `string` |  |  | "Osnr\u0028max/min/avg\u0029" |
| `data>>item>>min` | The minimum value of the metric (if applicable) | No | `string` |  |  | "0.0" |
| `data>>item>>rsName` | The resource name | Yes | `string` |  |  | "OTUC2-1-1-L1" |
| `code` | The status code of the operation | Yes | `number` |  |  | 0 |
| `msg` | A message indicating the result of the operation | Yes | `string` |  |  | "Operation is Successful" |

### Success Example
```json
{
    "total": 8,
    "data": [
        {
            "avg": "0.0",
            "collectTime": "2025-11-12 18:00:02",
            "id": 144,
            "max": "0.0",
            "metricName": "Osnr\u0028max/min/avg\u0029",
            "min": "0.0",
            "rsName": "OTUC2-1-1-L1"
        },
        {
            "collectTime": "2025-11-12 18:00:02",
            "id": 145,
            "metricName": "Pre Fec Ber\u0028max/min/avg\u0029",
            "rsName": "OTUC2-1-1-L1"
        },
        {
            "collectTime": "2025-11-12 18:00:02",
            "id": 146,
            "metricName": "Post Fec Ber\u0028max/min/avg\u0029",
            "rsName": "OTUC2-1-1-L1"
        },
        {
            "collectTime": "2025-11-12 18:00:02",
            "id": 147,
            "metricName": "Osnr\u0028max/min/avg\u0029",
            "rsName": "OTUC2-1-1-L2"
        },
        {
            "collectTime": "2025-11-12 18:00:02",
            "id": 148,
            "metricName": "Pre Fec Ber\u0028max/min/avg\u0029",
            "rsName": "OTUC2-1-1-L2"
        },
        {
            "collectTime": "2025-11-12 18:00:02",
            "id": 149,
            "metricName": "Post Fec Ber\u0028max/min/avg\u0029",
            "rsName": "OTUC2-1-1-L2"
        },
        {
            "avg": "0.0",
            "collectTime": "2025-11-12 18:00:02",
            "id": 150,
            "max": "0.0",
            "metricName": "Osnr\u0028max/min/avg\u0029",
            "min": "0.0",
            "rsName": "OCH-1-1-L1"
        },
        {
            "avg": "0.0",
            "collectTime": "2025-11-12 18:00:02",
            "id": 151,
            "max": "0.0",
            "metricName": "Osnr\u0028max/min/avg\u0029",
            "min": "0.0",
            "rsName": "OCH-1-1-L2"
        }
    ],
    "code": 0,
    "msg": "Operation is Successful"
}
```
