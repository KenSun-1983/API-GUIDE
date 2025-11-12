## API Information
This API is used to obtain port information by port name and network element ID.

### Detailed Explanation
There is no specific detailed explanation provided in the given content. You may need to refer to the system's official documentation for more in - depth information.

### API Path
`https://172.16.61.51/tiap_ems_wdm_mgt/tiap_ems_wdm_mgt/v1/netconf/port/get_port_by_name`

### Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| :--- | :--- | :--- | :--- | :--- | :--- |
| `_dc` | Timestamp - like parameter, might be used for cache - busting | Yes | `number` |  | 1762942864788 |
| `portFixName` | Fixed name of the port | Yes | `string` |  | PORT - 1 - 5 - 1 - APSS |
| `neId` | ID of the network element | Yes | `number` |  | 404 |

### Request Protocol
HTTP

### Request Method
GET (implied by `Invoke - WebRequest` without `-Method` specified as POST)

### Request Code Example (PowerShell)
```powershell
$session = New-Object Microsoft.PowerShell.Commands.WebRequestSession
$session.UserAgent = "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36"
$session.Cookies.Add((New-Object System.Net.Cookie("showLinkPort", "false", "/", "172.16.61.51")))
$session.Cookies.Add((New-Object System.Net.Cookie("showHostname", "false", "/", "172.16.61.51")))
$session.Cookies.Add((New-Object System.Net.Cookie("selTopoTypeId", "11_DCIBOX%20Device", "/", "172.16.61.51")))
$session.Cookies.Add((New-Object System.Net.Cookie("connect.sid", "s%3AzxHsOq7p259b8DsvTbhErduAB4aMbxFH.q%2FZT2B2FxT7ia3L%2FTZW3VKRQT3qFa%2FmXx6dGThQU9ms", "/", "172.16.61.51")))
$session.Cookies.Add((New-Object System.Net.Cookie("curSubnet", "403", "/", "172.16.61.51")))
Invoke-WebRequest -UseBasicParsing -Uri "https://172.16.61.51/tiap_ems_wdm_mgt/tiap_ems_wdm_mgt/v1/netconf/port/get_port_by_name?_dc=1762942864788&portFixName=PORT-1-5-1-APSS&neId=404" `
-WebSession $session `
-Headers @{
    "Accept"="*/*"
    "Accept-Encoding"="gzip, deflate, br, zstd"
    "Accept-Language"="zh-CN,zh;q=0.9"
    "Referer"="https://172.16.61.51/ui"
    "Sec-Fetch-Dest"="empty"
    "Sec-Fetch-Mode"="cors"
    "Sec-Fetch-Site"="same-origin"
    "X-Requested-With"="XMLHttpRequest"
    "sec-ch-ua"="`"Chromium`";v=`"142`", `"Google Chrome`";v=`"142`", `"Not_A Brand`";v=`"99`""
    "sec-ch-ua-mobile"="?0"
    "sec-ch-ua-platform"="`"Windows`""
}
```

### Response Content
**Return Result**
> Success (200)
JSON object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `code` | Operation result code | Yes | `number` |  |  | 0 |
| `msg` | Operation result message | Yes | `string` |  |  | "Operation is Successful" |
| `data` | Port information data | Yes | `object` |  |  |  |
| `data>>parent` | Parent component of the port | Yes | `string` |  |  | "OLP - 1 - 5" |
| `data>>oper - status` | Operational status of the port | Yes | `string` |  |  | "openconfig-platform-types:ACTIVE" |
| `data>>optical - port - type` | Optical port type | Yes | `string` |  |  | "openconfig-transport-types:BI" |
| `data>>panel - description` | Panel description of the port | Yes | `string` |  |  | "B" |
| `data>>description` | Description of the port | Yes | `string` |  |  | "1 - APSS" |
| `data>>admin - state` | Administrative state of the port | Yes | `string` |  |  | "ENABLED" |
| `data>>type` | Type of the port | Yes | `string` |  |  | "PORT" |
| `data>>outputPowerInstant` | Instantaneous output power | Yes | `string` |  |  | "-39.99" |
| `data>>empty` | Whether the port is empty | Yes | `boolean` |  |  | false |
| `data>>output - power` | Output power details | Yes | `object` |  |  |  |
| `data>>output - power>>avg` | Average output power | Yes | `number` |  |  | -39.99 |
| `data>>output - power>>min` | Minimum output power | Yes | `number` |  |  | -39.99 |
| `data>>output - power>>max - time` | Timestamp of the maximum output power | Yes | `number` |  |  | 1762942940602534040 |
| `data>>output - power>>max` | Maximum output power | Yes | `number` |  |  | -39.99 |
| `data>>output - power>>interval` | Sampling interval | Yes | `number` |  |  | 10000000000 |
| `data>>output - power>>min - time` | Timestamp of the minimum output power | Yes | `number` |  |  | 1762942936629370682 |
| `data>>output - power>>instant` | Instantaneous output power | Yes | `number` |  |  | -39.99 |
| `data>>input - power` | Input power details | Yes | `object` |  |  |  |
| `data>>input - power>>avg` | Average input power | Yes | `number` |  |  | -40.00 |
| `data>>input - power>>min` | Minimum input power | Yes | `number` |  |  | -40.00 |
| `data>>input - power>>max - time` | Timestamp of the maximum input power | Yes | `number` |  |  | 1762942941991434180 |
| `data>>input - power>>max` | Maximum input power | Yes | `number` |  |  | -40.00 |
| `data>>input - power>>interval` | Sampling interval | Yes | `number` |  |  | 10000000000 |
| `data>>input - power>>min - time` | Timestamp of the minimum input power | Yes | `number` |  |  | 1762942939876627718 |
| `data>>input - power>>instant` | Instantaneous input power | Yes | `number` |  |  | -40.00 |
| `data>>isFree` | Whether the port is free | Yes | `number` |  |  | 1 |
| `data>>inputPowerInstant` | Instantaneous input power (string format) | Yes | `string` |  |  | "-40.00" |
| `data>>name` | Name of the port | Yes | `string` |  |  | "PORT - 1 - 5 - 1 - APSS" |
| `data>>operStatus` | Operational status (simplified) | Yes | `string` |  |  | "ACTIVE" |
| `data>>location` | Location of the port | Yes | `string` |  |  | "1 - 5" |
| `data>>opticalPortType` | Optical port type (simplified) | Yes | `string` |  |  | "BI" |

### Success Example
```json
{
    "code": 0,
    "msg": "Operation is Successful",
    "data": {
        "parent": "OLP-1-5",
        "oper-status": "openconfig-platform-types:ACTIVE",
        "optical-port-type": "openconfig-transport-types:BI",
        "panel-description": "B",
        "description": "1-APSS",
        "admin-state": "ENABLED",
        "type": "PORT",
        "outputPowerInstant": "-39.99",
        "empty": false,
        "output-power": {
            "avg": -39.99,
            "min": -39.99,
            "max-time": 1762942940602534040,
            "max": -39.99,
            "interval": 10000000000,
            "min-time": 1762942936629370682,
            "instant": -39.99
        },
        "input-power": {
            "avg": -40.00,
            "min": -40.00,
            "max-time": 1762942941991434180,
            "max": -40.00,
            "interval": 10000000000,
            "min-time": 1762942939876627718,
            "instant": -40.00
        },
        "isFree": 1,
        "inputPowerInstant": "-40.00",
        "name": "PORT-1-5-1-APSS",
        "operStatus": "ACTIVE",
        "location": "1-5",
        "opticalPortType": "BI"
    }
}
```
