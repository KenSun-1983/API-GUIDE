# Query Optical Transceiver Information

## API Information
Query optical transceiver (optical module) information for a specific NE and card

## API Path
`http://XX.XX.XX.XX/tiap_ems_basic_mgt/tiap_ems_basic_mgt/v20/optical_transceiver`

## Request Protocol
HTTP

## Request Method
GET

## Query Parameters
| Parameter Name | Description | Required | Type | Restriction | Example |
| --- | --- | --- | --- | --- | --- |
| `neId` | Network Element ID | Yes | `number` | | 30 |
| `cardId` | Card ID (URL encoded) | Yes | `string` | Format: /ne={neId}/shelf={shelf}/slot={slot}/card={card} | `%2Fne%3D30%2Fshelf%3D1%2Fslot%3D11%2Fcard%3D1.1` |
| `page` | Page number | No | `number` | | 1 |
| `start` | Starting row number | No | `number` | | 0 |
| `limit` | Maximum number of rows returned | No | `number` | | 15 |

### Request Example
```
https://172.16.1.248/tiap_ems_basic_mgt/tiap_ems_basic_mgt/v20/optical_transceiver?neId=30&cardId=%2Fne%3D30%2Fshelf%3D1%2Fslot%3D11%2Fcard%3D1.1&page=1&start=0&limit=15
```

**Decoded cardId:**
```
/ne=30/shelf=1/slot=11/card=1.1
```

## Response Content
### Return Result
> Success (200)
Json array

| Parameter Name | Description | Required | Type | Data Dictionary | Restriction | Example |
| --- | --- | --- | --- | --- | --- | --- |
| `[0]` | Optical transceiver info item | Yes | `object` | | | See example below |
| `[0]>>biasCurrent` | Bias current | Yes | `string` | Unit: mA | | "39.408" |
| `[0]>>cfpSignalCodeType` | CFP signal code type | Yes | `string` | | | "" |
| `[0]>>ifIndex` | Interface index | Yes | `number` | | | 4 |
| `[0]>>indexInMib` | Index in MIB | Yes | `string` | | | "/ne=30/shelf=1/slot=11/card=1.1/port=3#portType=26" |
| `[0]>>maxWavelength` | Maximum wavelength | Yes | `string` | Unit: nm | | "" |
| `[0]>>minWavelength` | Minimum wavelength | Yes | `string` | Unit: nm | | "" |
| `[0]>>moduleSpeed` | Module speed | Yes | `string` | | | "" |
| `[0]>>moduleTemperature` | Module temperature | Yes | `string` | Unit: °C | | "41.941" |
| `[0]>>neId` | NE ID | Yes | `number` | | | 30 |
| `[0]>>opticalTransceiverAbility` | Optical transceiver ability | Yes | `string` | Hex code | | "00078020" |
| `[0]>>opticalTransceiverBRMax` | Max bit rate | Yes | `number` | Unit: Mbps | | 10300 |
| `[0]>>opticalTransceiverBRMin` | Min bit rate | Yes | `number` | Unit: Mbps | | 0 |
| `[0]>>opticalTransceiverCDR` | CDR (Clock Data Recovery) | Yes | `number` | 0 = Not supported<br>1 = Supported<br>2 = Unknown | | 2 |
| `[0]>>opticalTransceiverCMU` | CMU (Clock Multiplexing Unit) | Yes | `number` | 0 = Not supported<br>1 = Supported<br>2 = Unknown | | 2 |
| `[0]>>opticalTransceiverCalibrationType` | Calibration type | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverCompatibility` | Compatibility | Yes | `string` | | | "" |
| `[0]>>opticalTransceiverConnectorType` | Connector type | Yes | `number` | 8 = LC/PC | | 8 |
| `[0]>>opticalTransceiverCooled` | Cooled | Yes | `number` | 0 = Uncooled<br>1 = Cooled | | 0 |
| `[0]>>opticalTransceiverDDM` | DDM (Digital Diagnostic Monitoring) | Yes | `number` | 0 = Not supported<br>1 = Supported | | 1 |
| `[0]>>opticalTransceiverDetectorType` | Detector type | Yes | `number` | | | 0 |
| `[0]>>opticalTransceiverFEC` | FEC (Forward Error Correction) | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverInVpsLowPower` | In VPS low power | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverLineLoopBack` | Line loop back | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverMediaType` | Media type | Yes | `number` | | | 1 |
| `[0]>>opticalTransceiverOutVpsLowPower` | Out VPS low power | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverPowerDissipation` | Power dissipation | Yes | `number` | Unit: W | | 0 |
| `[0]>>opticalTransceiverRSSI` | RSSI (Received Signal Strength Indicator) | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverRefClock` | Reference clock | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverStandby` | Standby | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverTransmissionDistance` | Transmission distance | Yes | `string` | Unit: km | | "10" |
| `[0]>>opticalTransceiverTransmitterType` | Transmitter type | Yes | `number` | | | 0 |
| `[0]>>opticalTransceiverTunalable` | Tunable | Yes | `number` | 0 = Fixed<br>1 = Tunable<br>2 = Unknown | | 2 |
| `[0]>>opticalTransceiverTxDis` | TX Disable | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverType` | Transceiver type | Yes | `number` | 4 = SFP+ | | 4 |
| `[0]>>opticalTransceiverVendorName` | Vendor name | Yes | `string` | | | "Raisecom" |
| `[0]>>opticalTransceiverVendorPN` | Part number | Yes | `string` | | | "USFP+-192/S1" |
| `[0]>>opticalTransceiverVendorRev` | Revision | Yes | `string` | | | "1.0" |
| `[0]>>opticalTransceiverVendorSN` | Serial number | Yes | `string` | | | "823N8N3400147" |
| `[0]>>opticalTransceiverVps` | VPS | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverWaveTolerance` | Wave tolerance | Yes | `string` | Unit: nm | | "--" |
| `[0]>>opticalTransceiverWavelength` | Wavelength | Yes | `string` | Unit: nm | | "1310" |
| `[0]>>opticalTransceiverWavelengthContrl` | Wavelength control | Yes | `number` | | | 2 |
| `[0]>>opticalTransceiverXFILoopBack` | XFI loop back | Yes | `number` | | | 2 |
| `[0]>>portId` | Port ID | Yes | `string` | | | "/ne=30/shelf=1/slot=11/card=1.1/port=4#portType=262" |
| `[0]>>portName` | Port name | Yes | `string` | | | "11-Line4" |
| `[0]>>powerSupplyVoltage` | Power supply voltage | Yes | `string` | Unit: V | | "3.29" |
| `[0]>>protocolVersion` | Protocol version | Yes | `number` | | | 0 |
| `[0]>>receivedOpticalPowerDetectionType` | Received optical power detection type | Yes | `number` | | | 0 |
| `[0]>>rxOpticalPower` | Received optical power | Yes | `string` | Unit: dBm | | "-3.241" |
| `[0]>>rxOpticalPowerAlarmStatus` | RX alarm status | Yes | `string` | 0 = Normal<br>1 = Alarm | | "1" |
| `[0]>>rxOpticalPowerHighWarningThreshold` | RX high warning threshold | Yes | `string` | Unit: dBm | | "2.0" |
| `[0]>>rxOpticalPowerLowWarningThreshold` | RX low warning threshold | Yes | `string` | Unit: dBm | | "-15.406" |
| `[0]>>supportCdr` | Support CDR | Yes | `number` | | | 2 |
| `[0]>>txOpticalPower` | Transmit optical power | Yes | `string` | Unit: dBm | | "-2.332" |
| `[0]>>txOpticalPowerAlarmStatus` | TX alarm status | Yes | `string` | 0 = Normal<br>1 = Alarm | | "1" |
| `[0]>>txOpticalPowerHighWarningThreshold` | TX high warning threshold | Yes | `string` | Unit: dBm | | "2.0" |
| `[0]>>txOpticalPowerLowWarningThreshold` | TX low warning threshold | Yes | `string` | Unit: dBm | | "-9.2" |
| `[0]>>wheatherTunnable` | Whether tunable | Yes | `string` | 0 = Fixed<br>1 = Tunable<br>2 = Unknown | | "2" |

### Success Example
```json
[
    {
        "biasCurrent": "39.408",
        "cfpSignalCodeType": "",
        "ifIndex": 4,
        "indexInMib": "/ne=30/shelf=1/slot=11/card=1.1/port=3#portType=26",
        "maxWavelength": "",
        "minWavelength": "",
        "moduleSpeed": "",
        "moduleTemperature": "41.941",
        "neId": 30,
        "opticalTransceiverAbility": "00078020",
        "opticalTransceiverBRMax": 10300,
        "opticalTransceiverBRMin": 0,
        "opticalTransceiverCDR": 2,
        "opticalTransceiverCMU": 2,
        "opticalTransceiverCalibrationType": 2,
        "opticalTransceiverCompatibility": "",
        "opticalTransceiverConnectorType": 8,
        "opticalTransceiverCooled": 0,
        "opticalTransceiverDDM": 1,
        "opticalTransceiverDetectorType": 0,
        "opticalTransceiverFEC": 2,
        "opticalTransceiverInVpsLowPower": 2,
        "opticalTransceiverLineLoopBack": 2,
        "opticalTransceiverMediaType": 1,
        "opticalTransceiverOutVpsLowPower": 2,
        "opticalTransceiverPowerDissipation": 0,
        "opticalTransceiverRSSI": 2,
        "opticalTransceiverRefClock": 2,
        "opticalTransceiverStandby": 2,
        "opticalTransceiverTransmissionDistance": "10",
        "opticalTransceiverTransmitterType": 0,
        "opticalTransceiverTunalable": 2,
        "opticalTransceiverTxDis": 2,
        "opticalTransceiverType": 4,
        "opticalTransceiverVendorName": "Raisecom",
        "opticalTransceiverVendorPN": "USFP+-192/S1",
        "opticalTransceiverVendorRev": "1.0",
        "opticalTransceiverVendorSN": "823N8N3400147",
        "opticalTransceiverVps": 2,
        "opticalTransceiverWaveTolerance": "--",
        "opticalTransceiverWavelength": "1310",
        "opticalTransceiverWavelengthContrl": 2,
        "opticalTransceiverXFILoopBack": 2,
        "portId": "/ne=30/shelf=1/slot=11/card=1.1/port=4#portType=262",
        "portName": "11-Line4",
        "powerSupplyVoltage": "3.29",
        "protocolVersion": 0,
        "receivedOpticalPowerDetectionType": 0,
        "rxOpticalPower": "-3.241",
        "rxOpticalPowerAlarmStatus": "1",
        "rxOpticalPowerHighWarningThreshold": "2.0",
        "rxOpticalPowerLowWarningThreshold": "-15.406",
        "supportCdr": 2,
        "txOpticalPower": "-2.332",
        "txOpticalPowerAlarmStatus": "1",
        "txOpticalPowerHighWarningThreshold": "2.0",
        "txOpticalPowerLowWarningThreshold": "-9.2",
        "wheatherTunnable": "2"
    },
    {
        "biasCurrent": "30.15",
        "moduleTemperature": "40.835",
        "opticalTransceiverVendorName": "Raisecom",
        "opticalTransceiverVendorPN": "USFP+-192/S1",
        "opticalTransceiverVendorRev": "A",
        "opticalTransceiverVendorSN": "M5386J00644",
        "portName": "11-Line3",
        "rxOpticalPower": "-3.954",
        "txOpticalPower": "-3.254",
        "wavelength": "1310"
    }
]
```

## Key Monitoring Parameters

### Optical Power Metrics
| Parameter | Description | Unit | Normal Range | Alarm Thresholds |
|-----------|-------------|------|--------------|------------------|
| **txOpticalPower** | Transmit optical power | dBm | -9.2 ~ 2.0 | High: 2.0, Low: -9.2 |
| **rxOpticalPower** | Receive optical power | dBm | -15.4 ~ 2.0 | High: 2.0, Low: -15.4 |
| **biasCurrent** | Laser bias current | mA | Varies by module | - |

### Temperature & Voltage
| Parameter | Description | Unit | Example Value |
|-----------|-------------|------|---------------|
| **moduleTemperature** | Module operating temperature | °C | 41.941 |
| **powerSupplyVoltage** | Power supply voltage | V | 3.29 |

### Module Identification
| Parameter | Description | Example |
|-----------|-------------|---------|
| **opticalTransceiverVendorName** | Manufacturer | "Raisecom" |
| **opticalTransceiverVendorPN** | Part Number | "USFP+-192/S1" |
| **opticalTransceiverVendorSN** | Serial Number | "823N8N3400147" |
| **opticalTransceiverWavelength** | Operating wavelength | 1310 nm |
| **opticalTransceiverTransmissionDistance** | Transmission distance | 10 km |

## Data Dictionary

### Transceiver Type Codes
| Value | Description |
|-------|-------------|
| 4 | SFP+ |

### Connector Type Codes
| Value | Description |
|-------|-------------|
| 8 | LC/PC |

### Feature Support Codes
| Value | Description |
|-------|-------------|
| 0 | Not supported |
| 1 | Supported |
| 2 | Unknown |

Applies to: CDR, CMU, DDM, Tunable, RSSI, FEC, etc.

### Alarm Status Codes
| Value | Description |
|-------|-------------|
| 0 | Normal |
| 1 | Alarm |

## Usage Notes
1. **URL Encoding**: The `cardId` parameter must be URL-encoded
2. **Card ID Format**: `/ne={neId}/shelf={shelfId}/slot={slotId}/card={cardId}`
3. **Multiple Ports**: The API returns information for all ports on the specified card
4. **Alarm Monitoring**: Check `txOpticalPowerAlarmStatus` and `rxOpticalPowerAlarmStatus` for alarms
5. **Threshold Comparison**: Compare actual values with warning thresholds to assess module health

## Related Documentation
- [LLDP](../lldp.md) - LLDP neighbor information
- EMS basic management APIs
