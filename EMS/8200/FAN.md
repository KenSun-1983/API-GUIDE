# API Information
This API is used to obtain the fan list information.

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
`https://172.16.61.51/tiap_wdm_north/tiap_ems_wdm_mgt/v1/fan_config/fan_list_info?_dc=1762939398501`

### Request Protocol
HTTP

### Request Method
POST

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
| data>>item | The first fan information object | Yes | `object` |  |  |  |
| data>>item>>fanId | The ID of the fan | Yes | `string` |  |  | "1" |
| data>>item>>fanSpeed | The speed of the fan | Yes | `string` |  |  | "3240" |
| data>>item>>fanWorkingStatus | The working status of the fan | Yes | `string` |  |  | "normal" |
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
