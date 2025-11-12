# API Information
This API is used to obtain the fan list information.

### Detailed Explanation
The PowerShell script configures a web request session with specific cookies and headers, then sends a POST request to the specified API endpoint to get the fan list information.

### API Path
`https://172.16.61.51/tiap_ems_wdm_mgt/tiap_ems_wdm_mgt/v1/fan_config/fan_list_info?_dc=1762939398501`

### Request Protocol
HTTP

### Request Method
POST

### Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `_dc` | A timestamp-like parameter, possibly used for cache busting | Yes | `number` |  | 1762939398501 |

### Request Body
| Parameter Name | Description | Required | Type | Restriction | Example |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `neId` | The ID of the network element | Yes | `number` |  | 404 |
| `name` | The name of the fan | Yes | `string` |  | "FAN-1-14" |
| `page` | The page number | Yes | `number` |  | 1 |
| `start` | The starting index | Yes | `number` |  | 0 |
| `limit` | The maximum number of items per page | Yes | `number` |  | 50 |

### Request Body Example
```json
{"neId":404,"name":"FAN-1-14","page":1,"start":0,"limit":50}
```

### Response Content
#### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ |
| total | The total number of items | Yes | `number` |  |  | 0 |
| data | The list of fan information | Yes | `array` |  |  |  |
| data>>item[0] | The first fan information object | Yes | `object` |  |  |  |
| data>>item[0]>>fanId | The ID of the fan | Yes | `string` |  |  | "1" |
| data>>item[0]>>fanSpeed | The speed of the fan | Yes | `string` |  |  | "3240" |
| data>>item[0]>>fanWorkingStatus | The working status of the fan | Yes | `string` |  |  | "normal" |
| data>>item[1] | The second fan information object | Yes | `object` |  |  |  |
| data>>item[1]>>fanId | The ID of the fan | Yes | `string` |  |  | "2" |
| data>>item[1]>>fanSpeed | The speed of the fan | Yes | `string` |  |  | "3780" |
| data>>item[1]>>fanWorkingStatus | The working status of the fan | Yes | `string` |  |  | "normal" |
| code | The status code of the response | Yes | `number` |  |  | 0 |

#### Success Example
```json
{
    "total": 0,
    "data": [
        {
            "fanId": "1",
            "fanSpeed": "3240",
            "fanWorkingStatus": "normal"
        },
        {
            "fanId": "2",
            "fanSpeed": "3780",
            "fanWorkingStatus": "normal"
        }
    ],
    "code": 0
}
```
