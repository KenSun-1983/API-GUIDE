## API Information
Query performance data. Through this API, you can obtain performance - related information based on specified parameters.

### Detailed Explanation
- **Open API Interface**: There is no information about the specific steps for opening the API interface in the given content. You may need to refer to the system's official documentation or relevant configuration files.
- **How to get neId**: No information is provided on how to obtain the `neId` in the given content.

### API Path
`https://172.16.61.51/tiap_ems_wdm_mgt/tiap_ems_wdm_mgt/v1/performanceQuery/query_performance`

### Request Protocol
HTTP

### Request Method
POST

### Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `neId` | The ID of the network element | Yes | `number` |  | 404 |
| `fixedNetypeId` | Fixed network type ID | Yes | `number` |  | 20002 |
| `metricDetailList` | List of metric details | Yes | `array` |  | `[{"metricPairId":107}]` |
| `cardId` | Identifier for the card | Yes | `string` |  | `/ne=404/shelf=1/slot=1/card=1.1` |

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
