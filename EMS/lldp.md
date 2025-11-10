

# LLDP
## API Information
Obtain LLDP neighbor information. Through the data returned by this interface, you can acquire the peer device and port information connected to each port of the device.

**Detailed Explanation**:

***Open API Interface***
Log in to the server where RCView is installed and navigate to /comp/service/webapp/config/default.json in the installation directory.
In the file, locate the following section and add "/tiap_ems_north":"127.0.0.1:61308".

In the current version, the string "tiap_ems_north" can be specified arbitrarily, but it cannot be the same as any existing string. If you use another string, simply use your defined string in the API Path.

```json
"north": {
            "/couchdb": "127.0.0.1:5984",
            "/cloudvpn": "127.0.0.1:60150",
            "/alarm_north":"127.0.0.1:60030",
            "/tiap_ems_north":"127.0.0.1:61308",
            "/measure_sla_north":"127.0.0.1:61304"
        }
```

**API Path**
https://172.16.61.51/tiap_ems_north/tiap_ems_basic_mgt/v3/lldp_rem

**Request Protocol**
HTTP

**Request Method**
GET

**Request Header**:
| Header Label | Required | Description | Type | Data Dictionary | Restriction | Header Content | Example |
| :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ |
|Authentication-Token|Yes||[string]|||eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJhZG1pbmlzdHJhdG9yIiwiZXhwIjoxNzYyNzY5MzY5MTAwfQ.aOafEZY5Ok2AQRNruBa9AsfRxB8_tq5fnWlCVjDGvYQ|eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJpc3MiOiJhZG1pbmlzdHJhdG9yIiwiZXhwIjoxNzYyNzY5MzY5MTAwfQ.aOafEZY5Ok2AQRNruBa9AsfRxB8_tq5fnWlCVjDGvYQ|

**Query Parameters**:
| Parameter Name | Description | Required | Type | Restriction | Example |
| :------------ | :------------ | :------------ | :------------ | :------------ | :------------ |
|neId| |Yes|[string]||463|
|page| |Yes|[string]||1|
|start| |Yes|[string]||0|
|limit| |Yes|[string]||100|

**Response Content**:

**Return Result**
>Success (200)
Json
object

| Parameter Name  | Description | Required | Type | Data Dictionary | Restriction | Example |
| :------------ | :------------ | :------------ | :------------ | :------------ | :------------ | :------------ |
|total| |Yes|[number]| ||1|
|data| |Yes|[array]| ||[{"key":"463_Line 1","lldpRemChassisId":"a8:6d:5f:67:60:d1","lldpRemChassisIdSubtype":4,"lldpRemLocalPortNum":1,"lldpRemPortDesc":"port4","lldpRemPortId":"port4","lldpRemPortIdSubtype":5,"lldpRemSysCapEnabled":"","lldpRemSysCapSupported":"","lldpRemSysDesc":"Raisecom","lldpRemSysName":"Raisecom","neId":463,"portName":"Line 1"}]|
|data>>item[0]| |Yes|[object]| || |
|data>>item[0]>>key| |Yes|[string]| ||463_Line 1|
|data>>item[0]>>lldpRemChassisId| |Yes|[string]| ||a8:6d:5f:67:60:d1|
|data>>item[0]>>lldpRemChassisIdSubtype| |Yes|[number]| ||4|
|data>>item[0]>>lldpRemLocalPortNum| |Yes|[number]| ||1|
|data>>item[0]>>lldpRemPortDesc| |Yes|[string]| ||port4|
|data>>item[0]>>lldpRemPortId| |Yes|[string]| ||port4|
|data>>item[0]>>lldpRemPortIdSubtype| |Yes|[number]| ||5|
|data>>item[0]>>lldpRemSysCapEnabled| |Yes|[string]| || |
|data>>item[0]>>lldpRemSysCapSupported| |Yes|[string]| || |
|data>>item[0]>>lldpRemSysDesc| |Yes|[string]| ||Raisecom|
|data>>item[0]>>lldpRemSysName| |Yes|[string]| ||Raisecom|
|data>>item[0]>>neId| |Yes|[number]| ||463|
|data>>item[0]>>portName| |Yes|[string]| ||Line 1|
|code| |Yes|[number]| ||0|
|msg| |Yes|[string]| ||Operation is Successful|

**Success Example [Mock API]**:

**mock api**: https://result.eolink.com/9EmwBTE13c32db84bc562749eb3d17b83e5c24f2a3e2bb3?uri=https://172.16.61.51/tiap_ems_north/tiap_ems_basic_mgt/v3/lldp_rem&resultType=failure
```
{
    "total": 1,
    "data": [{
        "key": "463_Line 1",
        "lldpRemChassisId": "a8:6d:5f:67:60:d1",
        "lldpRemChassisIdSubtype": 4,
        "lldpRemLocalPortNum": 1,
        "lldpRemPortDesc": "port4",
        "lldpRemPortId": "port4",
        "lldpRemPortIdSubtype": 5,
        "lldpRemSysCapEnabled": "",
        "lldpRemSysCapSupported": "",
        "lldpRemSysDesc": "Raisecom",
        "lldpRemSysName": "Raisecom",
        "neId": 463,
        "portName": "Line 1"
    }],
    "code": 0,
    "msg": "Operation is Successful"
}
```

