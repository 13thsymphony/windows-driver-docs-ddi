---
UID: NS:ntddmmc._FEATURE_DATA_FIRMWARE_DATE
title: "_FEATURE_DATA_FIRMWARE_DATE"
author: windows-driver-content
description: The FEATURE_DATA_FIRMWARE_DATE structure holds the date information associated with the Firmware Information feature.
old-location: storage\feature_data_firmware_date.htm
old-project: storage
ms.assetid: 1f6c6a37-9510-47bc-b507-b3fd7477b432
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_FIRMWARE_DATE, FEATURE_DATA_FIRMWARE_DATE, FEATURE_DATA_FIRMWARE_DATE structure [Storage Devices], PFEATURE_DATA_FIRMWARE_DATE, PFEATURE_DATA_FIRMWARE_DATE structure pointer [Storage Devices], _FEATURE_DATA_FIRMWARE_DATE, ntddmmc/FEATURE_DATA_FIRMWARE_DATE, ntddmmc/PFEATURE_DATA_FIRMWARE_DATE, storage.feature_data_firmware_date, structs-CD-ROM_5e7edafb-823d-4e78-a601-a8f29c62ee4e.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddmmc.h
req.include-header: Ntddcdrm.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddmmc.h
api_name:
-	FEATURE_DATA_FIRMWARE_DATE
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_FIRMWARE_DATE, *PFEATURE_DATA_FIRMWARE_DATE
---

# _FEATURE_DATA_FIRMWARE_DATE structure
The FEATURE_DATA_FIRMWARE_DATE structure holds the date information associated with the Firmware Information feature.

## Syntax
```
typedef struct _FEATURE_DATA_FIRMWARE_DATE {
  FEATURE_HEADER Header;
  UCHAR          Year[4];
  UCHAR          Month[2];
  UCHAR          Day[2];
  UCHAR          Hour[2];
  UCHAR          Minute[2];
  UCHAR          Seconds[2];
  UCHAR          Reserved[2];
} *PFEATURE_DATA_FIRMWARE_DATE, FEATURE_DATA_FIRMWARE_DATE;
```

## Members


`Header`

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Year`

Contains the two low order decimal digits represented as ASCII characters that indicate the year. For example, if the year is 2013, the <b>Year</b> member will contain characters "33" (a hexadecimal value of 0x3133).

`Month`

Contains two decimal digits represented as ASCII characters that indicate the month. For example, if the month is August, the <b>Month</b> member will contain characters "08" (a hexadecimal value of 0x3038).

`Day`

Contains two decimal digits represented as ASCII characters that indicate the day. For example, if the day is August 12, the <b>Day</b> member will contain characters "12" (a hexadecimal value of 0x3132).

`Hour`

Contains two decimal digits represented as ASCII characters that indicate the hour. For example, if the time 1:20:43 PM, the <b>Hour</b> member will contain the characters "13" (hexadecimal value of 0x3133).

`Minute`

Contains two decimal digits represented as ASCII characters that indicates the minute of the hour. For example, if the time 1:20:43 PM, the <b>Minute</b> member will contain the characters "20" (hexadecimal value of 0x3230).

`Seconds`

Contains two decimal digits represented as ASCII characters that indicates the minute of the hour. For example, if the time 1:20:43 PM, the <b>Seconds</b> member will contain the characters "43" (hexadecimal value of 0x3433).

`Reserved`

Reserved.

## Remarks
The structure holds the date information associated with the feature named "Firmware Information" by the <i>SCSI Multimedia - 4</i> (<i>MMC-4</i>) specification. Devices that support this feature can be queried for the date and Greenwich Mean Time (GMT) of the creation of the firmware revision currently loaded on the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>