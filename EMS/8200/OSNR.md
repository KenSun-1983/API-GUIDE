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

### Request Body
| Parameter Name | Description | Required | Type | Restriction | Example |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `neId` | The ID of the network element | Yes | `number` |  | 404 |
| `fixedNetypeId` | Fixed network type ID | Yes | `number` |  | 20002 |
| `metricDetailList` | List of metric details | Yes | `array` |  | `[{"metricPairId":107}]` |
| `cardId` | Identifier for the card | Yes | `string` |  | `/ne=404/shelf=1/slot=1/card=1.1` |
### Request Body Example
```json
{
    "neId": 404,
    "fixedNetypeId": 20002,
    "metricDetailList": [
        {
            "metricPairId": 107
        }
    ],
    "cardId": "/ne=404/shelf=1/slot=1/card=1.1"
}
```
### Response Content
**Return Result**
> Success (200)
JSON object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `total` | Total number of data items | Yes | `number` |  |  | 4 |
| `data` | Array of performance data | Yes | `array` |  |  | `[{"avg":"0.0","collectTime":"2025-11-12 16:00:02","id":33,"max":"0.0","metricName":"Osnr\u0028max/min/avg\u0029","min":"0.0","rsName":"OTUC2-1-1-L1"},{"collectTime":"2025-11-12 16:00:02","id":34,"metricName":"Osnr\u0028max/min/avg\u0029","rsName":"OTUC2-1-1-L2"},{"avg":"0.0","collectTime":"2025-11-12 16:00:02","id":35,"max":"0.0","metricName":"Osnr\u0028max/min/avg\u0029","min":"0.0","rsName":"OCH-1-1-L1"},{"avg":"0.0","collectTime":"2025-11-12 16:00:02","id":36,"max":"0.0","metricName":"Osnr\u0028max/min/avg\u0029","min":"0.0","rsName":"OCH-1-1-L2"}]` |
| `data>>item[0]` | First item in the data array | Yes | `object` |  |  |  |
| `data>>item[0]>>avg` | Average value of the metric | No | `string` |  |  | "0.0" |
| `data>>item[0]>>collectTime` | Collection time of the performance data | Yes | `string` |  |  | "2025-11-12 16:00:02" |
| `data>>item[0]>>id` | Unique identifier of the performance data | Yes | `number` |  |  | 33 |
| `data>>item[0]>>max` | Maximum value of the metric | No | `string` |  |  | "0.0" |
| `data>>item[0]>>metricName` | Name of the metric | Yes | `string` |  |  | "Osnr(max/min/avg)" |
| `data>>item[0]>>min` | Minimum value of the metric | No | `string` |  |  | "0.0" |
| `data>>item[0]>>rsName` | Resource name | Yes | `string` |  |  | "OTUC2-1-1-L1" |
| `code` | Operation result code | Yes | `number` |  |  | 0 |
| `msg` | Operation result message | Yes | `string` |  |  | "Operation is Successful" |

### Success Example
```json
{
    "total": 4,
    "data": [
        {
            "avg": "0.0",
            "collectTime": "2025-11-12 16:00:02",
            "id": 33,
            "max": "0.0",
            "metricName": "Osnr\u0028max/min/avg\u0029",
            "min": "0.0",
            "rsName": "OTUC2-1-1-L1"
        },
        {
            "collectTime": "2025-11-12 16:00:02",
            "id": 34,
            "metricName": "Osnr\u0028max/min/avg\u0029",
            "rsName": "OTUC2-1-1-L2"
        },
        {
            "avg": "0.0",
            "collectTime": "2025-11-12 16:00:02",
            "id": 35,
            "max": "0.0",
            "metricName": "Osnr\u0028max/min/avg\u0029",
            "min": "0.0",
            "rsName": "OCH-1-1-L1"
        },
        {
            "avg": "0.0",
            "collectTime": "2025-11-12 16:00:02",
            "id": 36,
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
