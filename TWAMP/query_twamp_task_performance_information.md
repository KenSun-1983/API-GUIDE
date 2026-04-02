# Query TWAMP Task Performance Information

## API Information
Query and return performance information of a TWAMP task

## API Path
`http://XX.XX.XX.XX/measure_sla_north/measure_sla_config/v1/history_performance_data`

## Request Protocol
HTTP

## Request Method
GET

## Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `metricNames` | Metric names to query | Yes | `string` | Fixed format | `{"avail":10,"bw":0,"bwu":0,"fd":11,"flr":11,"ifdv":11}` |
| `e2eServiceId` | E2E service ID | Yes | `number` | From query all tasks API | 2 |
| `timeType` | Time type | Yes | `number` | 0 = Last hour<br>1 = Last day<br>2 = Last week<br>3 = Custom | 3 |
| `startTime` | Start time | No (Required if timeType=3) | `string` | Format: yyyy-MM-dd HH:mm:ss | "2024-01-01 10:44:32" |
| `endTime` | End time | No (Required if timeType=3) | `string` | Format: yyyy-MM-dd HH:mm:ss | "2024-01-02 10:44:34" |

### Request Example
```
https://172.16.68.15/measure_sla_north/measure_sla_config/v1/history_performance_data?timeType=3&startTime=2024-01-01 10:44:32&endTime=2024-01-02 10:44:34&metricNames={"avail":10,"bw":0,"bwu":0,"fd":11,"flr":11,"ifdv":11}&e2eServiceId=2
```

## Response Content
### Return Result
> Success (200)
Json object

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `avail` | Availability data | Yes | `array` | | | `[{"time":1703646000000}]` |
| `avail>>item[0]` | Availability item | | `object` | | | |
| `avail>>item[0]>>time` | Collection time | Yes | `number` | Unix timestamp (ms) | | 1703646000000 |
| `flr` | Frame Loss Ratio data | Yes | `array` | | | `[{"twMinFLR":"0.0",...}]` |
| `flr>>item[0]` | FLR item | | `object` | | | |
| `flr>>item[0]>>twMinFLR` | Minimum FLR value | Yes | `string` | | | "0.0" |
| `flr>>item[0]>>twAvgFLR` | Average FLR value | Yes | `string` | | | "0.0" |
| `flr>>item[0]>>twMaxFLR` | Maximum FLR value | Yes | `string` | | | "0.0" |
| `flr>>item[0]>>time` | Collection time | Yes | `number` | Unix timestamp (ms) | | 1703646000000 |
| `fd` | Frame Delay data | Yes | `array` | | | `[{"twMinFD":"0.318",...}]` |
| `fd>>item[0]` | FD item | | `object` | | | |
| `fd>>item[0]>>twMinFD` | Minimum delay value | Yes | `string` | | | "0.318" |
| `fd>>item[0]>>twAvgFD` | Average delay value | Yes | `string` | | | "0.401" |
| `fd>>item[0]>>twMaxFD` | Maximum delay value | Yes | `string` | | | "1.02" |
| `fd>>item[0]>>time` | Collection time | Yes | `number` | Unix timestamp (ms) | | 1703646000000 |
| `ifdv` | Inter-frame Delay Variation (Jitter) data | Yes | `array` | | | `[{"twMinIFDV":"0.0",...}]` |
| `ifdv>>item[0]` | IFDV item | | `object` | | | |
| `ifdv>>item[0]>>twMinIFDV` | Minimum jitter value | Yes | `string` | | | "0.0" |
| `ifdv>>item[0]>>twAvgIFDV` | Average jitter value | Yes | `string` | | | "0.034" |
| `ifdv>>item[0]>>twMaxIFDV` | Maximum jitter value | Yes | `string` | | | "0.646" |
| `ifdv>>item[0]>>time` | Collection time | Yes | `number` | Unix timestamp (ms) | | 1703646000000 |
| `status` | Query status | Yes | `string` | 0 = Success | | "0" |

### Success Example
```json
{
    "avail": [
        {
            "time": 1703646000000
        },
        {
            "time": 1703646300000
        },
        {
            "time": 1703646600000
        },
        {
            "time": 1703646900000
        },
        {
            "time": 1703647200000
        },
        {
            "time": 1703647500000
        },
        {
            "time": 1703647800000
        },
        {
            "time": 1703648100000
        },
        {
            "time": 1703648400000
        }
    ],
    "flr": [
        {
            "twMinFLR": "0.0",
            "twAvgFLR": "0.0",
            "twMaxFLR": "0.0",
            "time": 1703646000000
        },
        {
            "twMinFLR": "0.0",
            "twAvgFLR": "0.0",
            "twMaxFLR": "0.0",
            "time": 1703646300000
        },
        {
            "twMinFLR": "0.0",
            "twAvgFLR": "0.033",
            "twMaxFLR": "0.064",
            "time": 1703646600000
        }
    ],
    "fd": [
        {
            "twMaxFD": "1.02",
            "twAvgFD": "0.401",
            "time": 1703646000000,
            "twMinFD": "0.318"
        },
        {
            "twMaxFD": "0.47",
            "twAvgFD": "0.382",
            "time": 1703646300000,
            "twMinFD": "0.371"
        },
        {
            "twMaxFD": "6.241",
            "twAvgFD": "0.404",
            "time": 1703646600000,
            "twMinFD": "0.371"
        }
    ],
    "ifdv": [
        {
            "twMaxIFDV": "0.646",
            "twAvgIFDV": "0.034",
            "twMinIFDV": "0.0",
            "time": 1703646000000
        },
        {
            "twMaxIFDV": "0.086",
            "twAvgIFDV": "0.004",
            "twMinIFDV": "0.0",
            "time": 1703646300000
        },
        {
            "twMaxIFDV": "5.86",
            "twAvgIFDV": "0.045",
            "twMinIFDV": "0.0",
            "time": 1703646600000
        }
    ],
    "status": "0"
}
```

## Metric Explanation

### metricNames Parameter Format
```json
{
    "avail": 10,  // Availability (10 = enabled with detail)
    "bw": 0,      // Bandwidth (0 = disabled)
    "bwu": 0,     // Bandwidth utilization (0 = disabled)
    "fd": 11,     // Frame Delay (11 = enabled with min/avg/max)
    "flr": 11,    // Frame Loss Ratio (11 = enabled with min/avg/max)
    "ifdv": 11    // Inter-frame Delay Variation (11 = enabled with min/avg/max)
}
```

### Metric Value Codes
- **0**: Disabled/not queried
- **10**: Enabled with basic data
- **11**: Enabled with detailed statistics (min/avg/max)

### Performance Metrics

| Metric | Description | Unit | Typical Range |
|--------|-------------|------|---------------|
| **Availability** | Service availability percentage | % | 0-100 |
| **Frame Loss Ratio (FLR)** | Packet loss rate | % | 0-100 |
| **Frame Delay (FD)** | Network latency | ms | Varies by distance |
| **Inter-frame Delay Variation (IFDV)** | Jitter | ms | Lower is better |

## Usage Notes
1. **Prerequisite**: You must first call the "Query All TWAMP Tasks" API to get the `e2eServiceId`
2. **Time Format**: Timestamps are in milliseconds (Unix epoch time)
3. **Time Type Options**:
   - 0: Last hour - No need to specify startTime/endTime
   - 1: Last day - No need to specify startTime/endTime
   - 2: Last week - No need to specify startTime/endTime
   - 3: Custom - Must specify startTime and endTime
4. **Data Granularity**: Data points are typically collected at regular intervals (e.g., every 5-15 minutes)

## Related APIs
- [Query All TWAMP Tasks](query_all_twamp_tasks.md) - Get e2eServiceId
- [Query TWAMP Task Detailed Information](query_twamp_detailed_information.md) - Get task configuration details
