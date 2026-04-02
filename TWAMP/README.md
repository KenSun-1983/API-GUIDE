# TWAMP SLA Measurement APIs

## Overview
This directory contains REST API documentation for TWAMP (Two-Way Active Measurement Protocol) SLA measurement and performance query.

## API List

| # | API Name | File | Description | Method |
|---|----------|------|-------------|--------|
| 1 | [Query All TWAMP Tasks](query_all_twamp_tasks.md) | `query_all_twamp_tasks.md` | Query and return all TWAMP task information | PUT |
| 2 | [Query TWAMP Task Detailed Information](query_twamp_detailed_information.md) | `query_twamp_detailed_information.md` | Query detailed information of a specific TWAMP task | PUT |
| 3 | [Query TWAMP Task Performance Information](query_twamp_task_performance_information.md) | `query_twamp_task_performance_information.md` | Query performance metrics of a TWAMP task | GET |

## Configuration Instructions

### Northbound Interface Configuration
The request address for the northbound interface needs to be manually configured on site. Refer to Section 1.3.2 of the "REST Northbound Interface User Guide" for specific instructions.

## Typical Usage Flow

### Step 1: Query All TWAMP Tasks
Get the list of all configured TWAMP tasks and retrieve the `e2eServiceId` and `e2eServiceUrl`.

```bash
PUT /measure_sla_north/v1/twamp/e2e_service_information
{
    "page": 1,
    "start": 0,
    "limit": 15
}
```

**Key Response Fields:**
- `e2eServiceId`: Task ID (used in performance query)
- `e2eServiceUrl`: Task URL (used in detailed info query)
- `measureStatus`: 1 = Started
- `operateStatus`: 6 = Operation successful

### Step 2: Query Task Detailed Information
Use the `e2eServiceUrl` from Step 1 to get detailed task configuration.

```bash
PUT /measure_sla_north/v1/twamp/e2e_service_information
{
    "serviceType": 1,
    "e2eServiceUrl": "/e2e_service_id=518136620204921",
    "templateId": -1
}
```

**Key Response Fields:**
- `srcIp` / `destIp`: Source and destination IP addresses
- `srcNeLabel` / `destNeLabel`: Source and destination NE names
- `destUdpPort`: TWAMP UDP port (typically 862)
- `svlan`: Service VLAN ID

### Step 3: Query Task Performance Information
Use the `e2eServiceId` from Step 1 to query performance metrics.

```bash
GET /measure_sla_north/v1/history_performance_data?timeType=3&startTime=2024-01-01 10:44:32&endTime=2024-01-02 10:44:34&metricNames={"avail":10,"bw":0,"bwu":0,"fd":11,"flr":11,"ifdv":11}&e2eServiceId=2
```

**Available Metrics:**
- `avail`: Availability
- `flr`: Frame Loss Ratio (packet loss)
- `fd`: Frame Delay (latency)
- `ifdv`: Inter-frame Delay Variation (jitter)

## Performance Metrics Reference

### Metric Names Parameter Format
```json
{
    "avail": 10,  // Availability (10 = enabled with detail)
    "bw": 0,      // Bandwidth (0 = disabled)
    "bwu": 0,     // Bandwidth utilization (0 = disabled)
    "fd": 11,     // Frame Delay (11 = enabled with min/avg/max)
    "flr": 11,    // Frame Loss Ratio (11 = enabled with min/avg/max)
    "ifdv": 11    // IFDV/Jitter (11 = enabled with min/avg/max)
}
```

### Metric Value Codes
| Code | Description |
|------|-------------|
| 0 | Disabled/not queried |
| 10 | Enabled with basic data |
| 11 | Enabled with detailed statistics (min/avg/max) |

### Performance Metrics Table

| Metric | Full Name | Description | Unit | Better When |
|--------|-----------|-------------|------|-------------|
| **Availability** | Service Availability | Percentage of time service is available | % | Higher |
| **FLR** | Frame Loss Ratio | Packet loss rate | % | Lower |
| **FD** | Frame Delay | Network latency (one-way or round-trip) | ms | Lower |
| **IFDV** | Inter-frame Delay Variation | Jitter (delay variation) | ms | Lower |

## Time Type Options

| Value | Description | startTime/endTime Required |
|-------|-------------|---------------------------|
| 0 | Last hour | No |
| 1 | Last day | No |
| 2 | Last week | No |
| 3 | Custom time range | Yes |

## Common Status Codes

### Measure Status
| Value | Description |
|-------|-------------|
| 1 | Started/Active |

### Operate Status
| Value | Description |
|-------|-------------|
| 6 | Operation successful |

## Related Documentation
- Complete TWAMP API documentation (if available as a combined file)
- REST Northbound Interface User Guide

## Notes
1. All timestamps in responses are in milliseconds (Unix epoch time)
2. The e2eServiceId is a critical identifier used across multiple API calls
3. TWAMP uses UDP port 862 by default for test packets
4. Performance data granularity is typically 5-15 minutes depending on configuration
