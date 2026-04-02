# API Information
This API is used to get the list of TopoLink

## API Path
`https://172.16.61.51/north_topo/rest/topo/topo_link/link_info`

## Request Protocol
HTTP

## Request Method
GET
## Request Header

The header must contain user and Authentication-Token, where the value of user must be the same user who requested the token.

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
