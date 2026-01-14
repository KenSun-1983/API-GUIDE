# API Information
This API is used to get the list of TopoLink

## Detailed Explanation
AFTER RCView 3.2.10,Do not need this Step
***Open API Interface***
Log in to the server where RCView is installed and navigate to /comp/service/webapp/config/default.json in the installation directory.
In the file, locate the following section and add ""/north_topo":"127.0.0.1:3000".

In the current version, the string "north_topo" can be specified arbitrarily, but it cannot be the same as any existing string. If you use another string, simply use your defined string in the API Path.

```json
        "north": {
            "/couchdb": "127.0.0.1:5984",
            "/cloudvpn": "127.0.0.1:60150",
            "/alarm_north":"127.0.0.1:60030",
            "/tiap_ems_north":"127.0.0.1:61308",
            "/north_topo":"127.0.0.1:3000",
            "/measure_sla_north":"127.0.0.1:61304"
        },
```

## API Path
`https://172.16.61.51/north_topo/rest/topo/topo_link/link_info`

## Request Protocol
HTTP

## Request Method
GET

## Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
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

### Success Example
```json
{
    "success": true,
    "data": [
        {
            "link_symbol_id": 3,
            "link_name1": "1111",
            "remark": "",
            "direction": 2,
            "src_symbol_id": 9,
            "dest_symbol_id": 12,
            "src_port_id": "/ne=10/shelf=1/slot=3/card=1.1/port=1#portType=1",
            "des_port_id": "/ne=13/shelf=1/slot=5/card=1.1/port=8#portType=4996/subPort=4094#subPortType=351",
            "topo_type_id": "16",
            "minAlarmLevel": 10,
            "topo_type_name": "Common link",
            "anode_name": "neon",
            "znode_name": "10.200.199.170",
            "anode_port": "tdm1/3/1",
            "znode_port": "gigaethernet1/5/8.4094",
            "src_map_hierarchy": ",0,11,9,",
            "des_map_hierarchy": ",0,14,12,"
        }
    ],
    "total": 1
}
```
