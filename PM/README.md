# PM Performance Collection APIs

## Overview
This directory contains REST API documentation for Performance Management (PM) performance collection.

## API List

| # | API Name | File | Description |
|---|----------|------|-------------|
| 1 | [Query All PM Tasks](query_all_pm_tasks.md) | `query_all_pm_tasks.md` | Query all PM task information |
| 2 | [Query Device Performance Indicators](query_device_performance_indicators.md) | `query_device_performance_indicators.md` | Query specific NE performance indicators based on NE name |
| 3 | [Query Bandwidth History Data](query_bandwidth_history_data.md) | `query_bandwidth_history_data.md` | Query device bandwidth values within a time period |
| 4 | [Query Port+VLAN Rate Limit](query_port_vlan_rate_limit.md) | `query_port_vlan_rate_limit.md` | Query Port + VLAN rate limit configuration |

## Version History

| Version | Date | Description |
|---------|------|-------------|
| V1.0 | 2024-07-30 | Initial version |
| V2.0 | 2025-01-21 | Updated version |
| V3.0 | 2026-03-24 | Current version |

## Common Information

### Base URL
```
http://XX.XX.XX.XX:60040
```

### Main Metric Groups

**Business Traffic(Port+VLAN)** - Port and VLAN traffic metrics

| Metric Pair ID | Name | Unit | Description |
|----------------|------|------|-------------|
| 206 | In Octets | bytes | Inbound bytes |
| 207 | Out Octets | bytes | Outbound bytes |
| 208 | In Pkts | pkts | Inbound packets |
| 209 | Out Pkts | pkts | Outbound packets |
| 210 | CIR | kbps | Committed Information Rate |
| 211 | EIR | kbps | Excess Information Rate |

### Typical Usage Flow

1. **Query all PM tasks** to get the list of configured tasks
2. **Query device performance indicators** using `fixedNetypeId`, `taskId`, and `tmpId` from step 1
3. **Query bandwidth history data** using `metricGroupId`, `metricPairId`, and `detailId` from step 2
4. **Query Port+VLAN rate limit** to get bandwidth configuration for specific ports

## Related Documentation
- [Complete PM API Documentation](REST_API_Documentation_PM_V3.0.md) - Full combined documentation
