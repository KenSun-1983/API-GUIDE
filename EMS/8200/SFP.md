## API Information
Retrieve optical transceiver data. Through the data returned by this interface, you can acquire detailed information about the optical transceiver.

**Detailed Explanation**:
This API is used to get the data of optical transceivers. You can specify the network element ID, card ID, and pagination information in the request body.

**API Path**
https://172.16.61.51/tiap_ems_wdm_mgt/tiap_ems_wdm_mgt/v1/opticalTransceiver/getData?_dc=1762921493211

**Request Protocol**
HTTP

**Request Method**
POST

**Request Body**:
```json
{
    "neId": 254,
    "yangContainer": "components",
    "yangModule": "openconfig-platform",
    "cardId": "/ne=254/shelf=1/slot=7/card=1.1",
    "page": 1,
    "start": 0,
    "limit": 50
}
```

**Response Content**:

**Return Result**
>Success (200)
Json
object

| Parameter Name  | Description | Required | Type | Data Dictionary | Restriction | Example |
| :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ |
| code | Operation result code | Yes | [number] |  |  | 0 |
| msg | Operation result message | Yes | [string] |  |  | "Operation is Successful" |
| data | Array of optical transceiver data | Yes | [array] |  |  | See success example below |
| data>>item[0] | An item in the data array | Yes | [object] |  |  |  |
| data>>item[0]>>name | Name of the transceiver | Yes | [string] |  |  | "TRANSCEIVER-1-7-OSC" |
| data>>item[0]>>description | Description of the transceiver | Yes | [string] |  |  | "NON_PLUGGABLE" |
| data>>item[0]>>admin - state | Administrative state of the transceiver | Yes | [string] |  |  | "ENABLED" |
| data>>item[0]>>part - no | Part number of the transceiver | Yes | [string] |  |  | "1023152" |
| data>>item[0]>>parent | Parent component of the transceiver | Yes | [string] |  |  | "PORT-1-7-OSC" |
| data>>item[0]>>firmware - version | Firmware version of the transceiver | Yes | [string] |  |  | "1.0.0" |
| data>>item[0]>>hardware - version | Hardware version of the transceiver | Yes | [string] |  |  | "1.0.0" |
| data>>item[0]>>oper - status | Operational status of the transceiver | Yes | [string] |  |  | "ACTIVE" |
| data>>item[0]>>mfg - name | Manufacturer name of the transceiver | Yes | [string] |  |  | "Raisecom" |
| data>>item[0]>>serial - no | Serial number of the transceiver | Yes | [string] |  |  | "03109S21A09U0070" |
| data>>item[0]>>mfg - date | Manufacturing date of the transceiver | Yes | [string] |  |  | "2000-01-01" |
| data>>item[0]>>type | Type of the transceiver | Yes | [string] |  |  | "TRANSCEIVER" |
| data>>item[0]>>empty | Whether the transceiver is empty | Yes | [boolean] |  |  | false |
| data>>item[0]>>software - version | Software version of the transceiver | Yes | [string] |  |  | "1.0.0" |
| data>>item[0]>>removable | Whether the transceiver is removable | Yes | [boolean] |  |  | true |
| data>>item[0]>>temperature | Temperature information of the transceiver | Yes | [object] |  |  |  |
| data>>item[0]>>temperature>>min | Minimum temperature | Yes | [number] |  |  | 0.0 |
| data>>item[0]>>temperature>>avg | Average temperature | Yes | [number] |  |  | 0.0 |
| data>>item[0]>>temperature>>max - time | Time when the maximum temperature occurred | Yes | [number] |  |  | 0 |
| data>>item[0]>>temperature>>max | Maximum temperature | Yes | [number] |  |  | 0.0 |
| data>>item[0]>>temperature>>interval | Interval for temperature measurement | Yes | [number] |  |  | 0 |
| data>>item[0]>>temperature>>min - time | Time when the minimum temperature occurred | Yes | [number] |  |  | 0 |
| data>>item[0]>>temperature>>instant | Instantaneous temperature | Yes | [number] |  |  | 29.0 |
| data>>item[0]>>location | Location of the transceiver | Yes | [string] |  |  | "1-7" |
| data>>item[0]>>instant | Instantaneous value (same as temperature.instant in this case) | Yes | [number] |  |  | 29.0 |
| data>>item[0]>>transceiver - serial - no | Serial number of the transceiver | Yes | [string] |  |  | "03109S21A09U0070" |
| data>>item[0]>>used - service - port - type - preconf | Pre - configured used service port type | Yes | [string] |  |  | "openconfig-transport-types:PT_100M" |
| data>>item[0]>>supported - service - port - types | Supported service port types | Yes | [object] |  |  |  |
| data>>item[0]>>supported - service - port - types>>supported - service - port - type | Array of supported service port types | Yes | [array] |  |  | ["openconfig-transport-types:PT_100M"] |
| data>>item[0]>>used - service - port - type | Used service port type | Yes | [string] |  |  | "PT_100M" |
| data>>item[0]>>compliance - code | Compliance code of the transceiver | Yes | [string] |  |  | "UNDEFINE" |
| data>>item[0]>>form - factor | Form factor of the transceiver | Yes | [string] |  |  | "SFP" |
| data>>item[0]>>fault - condition | Whether there is a fault condition | Yes | [boolean] |  |  | true |
| data>>item[0]>>enabled | Whether the transceiver is enabled | Yes | [boolean] |  |  | true |
| data>>item[0]>>date - code | Date code of the transceiver | Yes | [string] |  |  | "2021-10-13T08:00:00+08:00" |
| data>>item[0]>>connector - type | Connector type of the transceiver | Yes | [string] |  |  | "LC_CONNECTOR" |
| data>>item[0]>>output - power | Output power information of the transceiver | Yes | [object] |  |  |  |
| data>>item[0]>>output - power>>avg | Average output power | Yes | [number] |  |  | 0.70 |
| data>>item[0]>>output - power>>min | Minimum output power | Yes | [number] |  |  | 0.67 |
| data>>item[0]>>output - power>>max - time | Time when the maximum output power occurred | Yes | [number] |  |  | 1762921566177595627 |
| data>>item[0]>>output - power>>max | Maximum output power | Yes | [number] |  |  | 0.72 |
| data>>item[0]>>output - power>>interval | Interval for output power measurement | Yes | [number] |  |  | 10000000000 |
| data>>item[0]>>output - power>>min - time | Time when the minimum output power occurred | Yes | [number] |  |  | 1762921567310564244 |
| data>>item[0]>>output - power>>instant | Instantaneous output power | Yes | [number] |  |  | 0.70 |
| data>>item[0]>>input - power | Input power information of the transceiver | Yes | [object] |  |  |  |
| data>>item[0]>>input - power>>avg | Average input power | Yes | [number] |  |  | - 40.00 |
| data>>item[0]>>input - power>>min | Minimum input power | Yes | [number] |  |  | - 40.00 |
| data>>item[0]>>input - power>>max - time | Time when the maximum input power occurred | Yes | [number] |  |  | 1762921563556941346 |
| data>>item[0]>>input - power>>max | Maximum input power | Yes | [number] |  |  | - 40.00 |
| data>>item[0]>>input - power>>interval | Interval for input power measurement | Yes | [number] |  | | 10000000000 |
| data>>item[0]>>input - power>>min - time | Time when the minimum input power occurred | Yes | [number] |  |  | 1762921562266354154 |
| data>>item[0]>>input - power>>instant | Instantaneous input power | Yes | [number] |  |  | - 40.00 |
| data>>item[0]>>vendor | Vendor of the transceiver | Yes | [string] |  |  | "null" |
| data>>item[0]>>usedServicePortTypePreconf | Pre - configured used service port type (duplicate with used - service - port - type - preconf) | Yes | [string] |  |  | "PT_100M" |
| data>>item[0]>>support - port - speed - types | Supported port speed types | Yes | [string] |  |  | "PT_100M" |
| data>>item[0]>>input - power - instant | Instantaneous input power (duplicate with input - power.instant) | Yes | [number] |  |  | - 40.00 |
| data>>item[0]>>output - power - instant | Instantaneous output power (duplicate with output - power.instant) | Yes | [number] |  |  | 0.70 |


***Success Example***:
```json
{
    "code": 0,
    "msg": "Operation is Successful",
    "data": [
        {
            "name": "TRANSCEIVER-1-7-OSC",
            "description": "NON_PLUGGABLE",
            "admin-state": "ENABLED",
            "part-no": "1023152",
            "parent": "PORT-1-7-OSC",
            "firmware-version": "1.0.0",
            "hardware-version": "1.0.0",
            "oper-status": "ACTIVE",
            "mfg-name": "Raisecom",
            "serial-no": "03109S21A09U0070",
            "mfg-date": "2000-01-01",
            "type": "TRANSCEIVER",
            "empty": false,
            "software-version": "1.0.0",
            "removable": true,
            "temperature": {
                "min": 0.0,
                "avg": 0.0,
                "max-time": 0,
                "max": 0.0,
                "interval": 0,
                "min-time": 0,
                "instant": 29.0
            },
            "location": "1-7",
            "instant": 29.0,
            "transceiver-serial-no": "03109S21A09U0070",
            "used-service-port-type-preconf": "openconfig-transport-types:PT_100M",
            "supported-service-port-types": {
                "supported-service-port-type": [
                    "openconfig-transport-types:PT_100M"
                ]
            },
            "used-service-port-type": "PT_100M",
            "compliance-code": "UNDEFINE",
            "form-factor": "SFP",
            "fault-condition": true,
            "enabled": true,
            "date-code": "2021-10-13T08:00:00+08:00",
            "connector-type": "LC_CONNECTOR",
            "output-power": {
                "avg": 0.70,
                "min": 0.67,
                "max-time": 1762921566177595627,
                "max": 0.72,
                "interval": 10000000000,
                "min-time": 1762921567310564244,
                "instant": 0.70
            },
            "input-power": {
                "avg": -40.00,
                "min": -40.00,
                "max-time": 1762921563556941346,
                "max": -40.00,
                "interval": 10000000000,
                "min-time": 1762921562266354154,
                "instant": -40.00
            },
            "vendor": "null",
            "usedServicePortTypePreconf": "PT_100M",
            "support-port-speed-types": "PT_100M",
            "input-power-instant": -40.00,
            "output-power-instant": 0.70
        }
    ]
}
```
