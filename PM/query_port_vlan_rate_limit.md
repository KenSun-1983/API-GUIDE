# Query Port+VLAN Rate Limit

## API Information
Query the rate limit configuration of Port + VLAN

## API Path
`http://XX.XX.XX.XX/tiap_ems_north/tiap_ems_basic_mgt/v20/port_rate_limit`

## Request Protocol
HTTP

## Request Method
GET

## Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `neId` | NE ID | Yes | `number` | | 2640 |
| `page` | Page number | No | `number` | | 1 |
| `start` | Starting row number | No | `number` | | 0 |
| `limit` | Maximum number of rows returned each time | No | `number` | | 100 |

## Request Body
None

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `total` | Total number of records | Yes | `number` | | | 1 |
| `data` | Rate limit configuration list | Yes | `array` | | `[{"cbs":111,...}]` |
| `data>>item[0]` | Rate limit configuration item | Yes | `object` | | | |
| `data>>item[0]>>cbs` | Committed Burst Size | Yes | `number` | | | 111 |
| `data>>item[0]>>cir` | Committed Information Rate | Yes | `number` | | | 1111 |
| `data>>item[0]>>direction` | Rate limit direction | Yes | `number` | 1 = OUT<br>2 = IN | Enumerated values: 1, 2 | 2 |
| `data>>item[0]>>ebs` | Excess Burst Size | Yes | `number` | | | 111 |
| `data>>item[0]>>eir` | Excess Information Rate | Yes | `number` | | | 1111 |
| `data>>item[0]>>id` | Configuration ID | Yes | `number` | | | 1138 |
| `data>>item[0]>>neId` | NE ID | Yes | `number` | | | 2640 |
| `data>>item[0]>>portIndex` | Port index | Yes | `string` | | | "3" |
| `data>>item[0]>>portName` | Port name | Yes | `string` | | | "Client 1" |
| `data>>item[0]>>statsEnable` | Statistics enable | Yes | `number` | 1 = Enable<br>2 = Disable | Enumerated values: 1, 2 | 1 |
| `data>>item[0]>>vlanId` | VLAN ID | Yes | `number` | | | 11 |
| `code` | Response code | Yes | `number` | | | 0 |

### Success Example
```json
{
    "total": 1,
    "data": [
        {
            "cbs": 111,
            "cir": 1111,
            "direction": 2,
            "ebs": 111,
            "eir": 1111,
            "id": 1138,
            "neId": 2640,
            "portIndex": "3",
            "portName": "Client 1",
            "statsEnable": 1,
            "vlanId": 11
        }
    ],
    "code": 0
}
```

## Data Dictionary

### Direction (Rate Limit Direction)
| Value | Description |
| --- | --- |
| 1 | OUT - Outbound direction |
| 2 | IN - Inbound direction |

### StatsEnable (Statistics Enable)
| Value | Description |
| --- | --- |
| 1 | Enable - Statistics collection enabled |
| 2 | Disable - Statistics collection disabled |

## Related Metrics
- **CIR (Committed Information Rate)**: The guaranteed bandwidth in kbps
- **EIR (Excess Information Rate)**: The excess bandwidth available beyond CIR in kbps
- **CBS (Committed Burst Size)**: The maximum burst size for committed rate
- **EBS (Excess Burst Size)**: The maximum burst size for excess rate
