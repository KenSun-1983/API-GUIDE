# API Information
This API is used to get the list of optical amplifiers by network element ID and card ID.

## Detailed Explanation
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

## API Path
`https://172.16.61.51/tiap_wdm_north/tiap_ems_wdm_mgt/v1/netconf/optical_amplifier/get_list_by_neid_cardid`

## Request Protocol
HTTP

## Request Method
POST

## Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `neId` | The ID of the network element | Yes | `number` |  | 404 |
| `cardId` | The ID of the card | Yes | `string` |  | `/ne=404/shelf=1/slot=8/card=1.1` |
| `page` | The page number | Yes | `number` |  | 1 |
| `start` | The starting index | Yes | `number` |  | 0 |
| `limit` | The maximum number of items per page | Yes | `number` |  | 25 |

## Request Body
None

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `code` | The status code of the operation | Yes | `number` |  |  | 0 |
| `msg` | A message indicating the result of the operation | Yes | `string` |  |  | "Operation is Successful" |
| `data` | The data part of the response | Yes | `array` |  |  |  |
| `data>>item[0]` | The first item in the data array | Yes | `object` |  |  |  |
| `data>>item[0]>>rc - optical - amplifier:target - laser - bias - current` | The target laser bias current | Yes | `number` |  |  | 300.00 |
| `data>>item[0]>>target - gain` | The target gain | Yes | `number` |  |  | 22.00 |
| `data>>item[0]>>target - output - power` | The target output power | Yes | `number` |  |  | 6.00 |
| `data>>item[0]>>target - voa - attenuation` | The target VOA attenuation | Yes | `number` |  |  | 3.00 |
| `data>>item[0]>>name` | The name of the optical amplifier | Yes | `string` |  |  | "EDFA - 1 - 8 - FGA" |
| `data>>item[0]>>amp - mode` | The amplifier mode | Yes | `string` |  |  | "openconfig - optical - amplifier:CONSTANT_GAIN" |
| `data>>item[0]>>apr - enable` | Whether APR is enabled | Yes | `string` |  |  | "DISABLE" |
| `data>>item[0]>>target - gain - tilt` | The target gain tilt | Yes | `number` |  |  | 0.0 |
| `data>>item[0]>>enabled` | Whether the amplifier is enabled | Yes | `boolean` |  |  | true |
| `data>>item[0]>>optical - return - loss` | The optical return loss information | Yes | `object` |  |  |  |
| `data>>item[0]>>optical - return - loss>>avg` | The average optical return loss | Yes | `number` |  |  | 45.00 |
| `data>>item[0]>>optical - return - loss>>min` | The minimum optical return loss | Yes | `number` |  |  | 45.00 |
| `data>>item[0]>>optical - return - loss>>max - time` | The time when the maximum optical return loss occurred | Yes | `number` |  |  | 1762939697059319734 |
| `data>>item[0]>>optical - return - loss>>max` | The maximum optical return loss | Yes | `number` |  |  | 45.00 |
| `data>>item[0]>>optical - return - loss>>interval` | The interval for data collection | Yes | `number` |  |  | 10000000000 |
| `data>>item[0]>>optical - return - loss>>min - time` | The time when the minimum optical return loss occurred | Yes | `number` |  |  | 1762939695733753937 |
| `data>>item[0]>>optical - return - loss>>instant` | The instant optical return loss | Yes | `number` |  |  | 45.00 |
| `data>>item[0]>>laser - bias - current` | The laser bias current information | Yes | `object` |  |  |  |
| `data>>item[0]>>laser - bias - current>>avg` | The average laser bias current | Yes | `number` |  |  | 296.59 |
| `data>>item[0]>>laser - bias - current>>min` | The minimum laser bias current | Yes | `number` |  |  | 294.29 |
| `data>>item[0]>>laser - bias - current>>max - time` | The time when the maximum laser bias current occurred | Yes | `number` |  |  | 1762939696424410577 |
| `data>>item[0]>>laser - bias - current>>max` | The maximum laser bias current | Yes | `number` |  |  | 299.10 |
| `data>>item[0]>>laser - bias - current>>interval` | The interval for data collection | Yes | `number` |  |  | 10000000000 |
| `data>>item[0]>>laser - bias - current>>min - time` | The time when the minimum laser bias current occurred | Yes | `number` |  |  | 1762939700049615076 |
| `data>>item[0]>>laser - bias - current>>instant` | The instant laser bias current | Yes | `number` |  |  | 294.79 |
| `data>>item[0]>>type` | The type of the amplifier | Yes | `string` |  |  | "EDFA" |
| `data>>item[0]>>actual - gain - tilt` | The actual gain tilt information | Yes | `object` |  |  |  |
| `data>>item[0]>>actual - gain - tilt>>avg` | The average actual gain tilt | Yes | `number` |  |  | 0.0 |
| `data>>item[0]>>actual - gain - tilt>>min` | The minimum actual gain tilt | Yes | `number` |  |  | 0.0 |
| `data>>item[0]>>actual - gain - tilt>>max - time` | The time when the maximum actual gain tilt occurred | Yes | `number` |  |  | 1762939695847472903 |
| `data>>item[0]>>actual - gain - tilt>>max` | The maximum actual gain tilt | Yes | `number` |  |  | 0.0 |
| `data>>item[0]>>actual - gain - tilt>>interval` | The interval for data collection | Yes | `number` |  |  | 10000000000 |
| `data>>item[0]>>actual - gain - tilt>>min - time` | The time when the minimum actual gain tilt occurred | Yes | `number` |  |  | 1762939702770150520 |
| `data>>item[0]>>actual - gain - tilt>>instant` | The instant actual gain tilt | Yes | `number` |  |  | 0.0 |
| `data>>item[0]>>ingress - port` | The ingress port of the amplifier | Yes | `string` |  |  | "PORT - 1 - 8 - EDFAIN" |
| `data>>item[0]>>output - power` | The output power information | Yes | `object` |  |  |  |
| `data>>item[0]>>output - power>>avg` | The average output power | Yes | `number` |  |  | 17.06 |
| `data>>item[0]>>output - power>>min` | The minimum output power | Yes | `number` |  |  | 17.00 |
| `data>>item[0]>>output - power>>max - time` | The time when the maximum output power occurred | Yes | `number` |  |  | 1762939696906546951 |
| `data>>item[0]>>output - power>>max` | The maximum output power | Yes | `number` |  |  | 17.09 |
| `data>>item[0]>>output - power>>interval` | The interval for data collection | Yes | `number` |  |  | 10000000000 |
| `data>>item[0]>>output - power>>min - time` | The time when the minimum output power occurred | Yes | `number` |  |  | 1762939698227248123 |
| `data>>item[0]>>output - power>>instant` | The instant output power | Yes | `number` |  |  | 17.00 |
| `data>>item[0]>>actual - gain` | The actual gain information | Yes | `object` |  |  |  |
| `data>>item[0]>>actual - gain>>instant` | The instant actual gain | Yes | `number` |  |  | 21.80 |
| `data>>item[0]>>input - power` | The input power information | Yes | `object` |  |  |  |
| `data>>item[0]>>input - power>>avg` | The average input power | Yes | `number` |  |  | - 4.80 |
| `data>>item[0]>>input - power>>min` | The minimum input power | Yes | `number` |  |  | - 4.80 |
| `data>>item[0]>>input - power>>max - time` | The time when the maximum input power occurred | Yes | `number` |  |  | 1762939700547321713 |
| `data>>item[0]>>input - power>>max` | The maximum input power | Yes | `number` |  |  | - 4.80 |
| `data>>item[0]>>input - power>>interval` | The interval for data collection | Yes | `number` |  |  | 10000000000 |
| `data>>item[0]>>input - power>>min - time` | The time when the minimum input power occurred | Yes | `number` |  |  | 1762939695278614575 |
| `data>>item[0]>>input - power>>instant` | The instant input power | Yes | `number` |  |  | - 4.80 |
| `data>>item[0]>>egress - port` | The egress port of the amplifier | Yes | `string` |  |  | "PORT - 1 - 8 - EDFAOUT" |
| `data>>item[0]>>actual - voa - attenuation` | The actual VOA attenuation | Yes | `number` |  |  | 4.77 |
| `data>>item[0]>>rc - optical - amplifier:panel - switch - ready` | Whether the panel switch is ready | Yes | `boolean` |  |  | false |
| `data>>item[0]>>actualGainInstant` | The instant actual gain as a string | Yes | `string` |  |  | "21.80" |
| `data>>item[0]>>actualGainTiltInstant` | The instant actual gain tilt as a string | Yes | `string` |  |  | "0.0" |
| `data>>item[0]>>inputPowerInstant` | The instant input power as a string | Yes | `string` |  |  | "-4.80" |
| `data>>item[0]>>outputPowerInstant` | The instant output power as a string | Yes | `string` |  |  | "17.00" |
| `data>>item[0]>>laserBiasCurrentInstant` | The instant laser bias current as a string | Yes | `string` |  |  | "294.79" |
| `data>>item[0]>>opticalReturnLossInstant` | The instant optical return loss as a string | Yes | `string` |  |  | "45.00" |
| `data>>item[0]>>ampMode` | The amplifier mode (simplified) | Yes | `string` |  |  | "CONSTANT_GAIN" |
| `data>>item[0]>>target - laser - bias - current` | The target laser bias current | Yes | `number` |  |  | 300.00 |
| `data>>item[0]>>panelSwitchReady` | Whether the panel switch is ready | Yes | `boolean` |  |  | false |


### Success Example
```json
{
    "code": 0,
    "msg": "Operation is Successful",
    "data": [
        {
            "rc-optical-amplifier:target-laser-bias-current": 300.00,
            "target-gain": 22.00,
            "target-output-power": 6.00,
            "target-voa-attenuation": 3.00,
            "name": "EDFA-1-8-FGA",
            "amp-mode": "openconfig-optical-amplifier:CONSTANT_GAIN",
            "apr-enable": "DISABLE",
            "target-gain-tilt": 0.0,
            "enabled": true,
            "optical-return-loss": {
                "avg": 45.00,
                "min": 45.00,
                "max-time": 1762939697059319734,
                "max": 45.00,
                "interval": 10000000000,
                "min-time": 1762939695733753937,
                "instant": 45.00
            },
            "laser-bias-current": {
                "avg": 296.59,
                "min": 294.29,
                "max-time": 1762939696424410577,
                "max": 299.10,
                "interval": 10000000000,
                "min-time": 1762939700049615076,
                "instant": 294.79
            },
            "type": "EDFA",
            "actual-gain-tilt": {
                "avg": 0.0,
                "min": 0.0,
                "max-time": 1762939695847472903,
                "max": 0.0,
                "interval": 10000000000,
                "min-time": 1762939702770150520,
                "instant": 0.0
            },
            "ingress-port": "PORT-1-8-EDFAIN",
            "output-power": {
                "avg": 17.06,
                "min": 17.00,
                "max-time": 1762939696906546951,
"max": 17.09,
                "interval": 10000000000,
                "min-time": 1762939698227248123,
                "instant": 17.00
            },
            "actual-gain": {
                "instant": 21.80
            },
            "input-power": {
                "avg": -4.80,
                "min": -4.80,
                "max-time": 1762939700547321713,
                "max": -4.80,
                "interval": 10000000000,
                "min-time": 1762939695278614575,
                "instant": -4.80
            },
            "egress-port": "PORT-1-8-EDFAOUT",
            "actual-voa-attenuation": 4.77,
            "rc-optical-amplifier:panel-switch-ready": false,
            "actualGainInstant": "21.80",
            "actualGainTiltInstant": "0.0",
            "inputPowerInstant": "-4.80",
            "outputPowerInstant": "17.00",
            "laserBiasCurrentInstant": "294.79",
            "opticalReturnLossInstant": "45.00",
            "ampMode": "CONSTANT_GAIN",
            "target-laser-bias-current": 300.00,
            "panelSwitchReady": false
        }
    ]
}
```
