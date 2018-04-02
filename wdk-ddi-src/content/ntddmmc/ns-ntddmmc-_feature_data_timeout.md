---
UID: NS:ntddmmc._FEATURE_DATA_TIMEOUT
title: "_FEATURE_DATA_TIMEOUT"
author: windows-driver-content
description: The FEATURE_DATA_TIMEOUT structure holds information about the Time-Out feature.
old-location: storage\feature_data_timeout.htm
old-project: storage
ms.assetid: 0699dcc3-ab43-436e-b7d3-09898e4d823c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_TIMEOUT, FEATURE_DATA_TIMEOUT, FEATURE_DATA_TIMEOUT structure [Storage Devices], PFEATURE_DATA_TIMEOUT, PFEATURE_DATA_TIMEOUT structure pointer [Storage Devices], _FEATURE_DATA_TIMEOUT, ntddmmc/FEATURE_DATA_TIMEOUT, ntddmmc/PFEATURE_DATA_TIMEOUT, storage.feature_data_timeout, structs-CD-ROM_2de49c50-b26e-42c0-b637-40f752b59891.xml"
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
-	FEATURE_DATA_TIMEOUT
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_TIMEOUT, *PFEATURE_DATA_TIMEOUT
---

# _FEATURE_DATA_TIMEOUT structure
The FEATURE_DATA_TIMEOUT structure holds information about the Time-Out feature.

## Syntax
```
typedef struct _FEATURE_DATA_TIMEOUT {
  FEATURE_HEADER Header;
  UCHAR  : 1     Group3;
  UCHAR  : 7     Reserved1;
  UCHAR          Reserved2;
  UCHAR          UnitLength[2];
} *PFEATURE_DATA_TIMEOUT, FEATURE_DATA_TIMEOUT;
```

## Members


`Header`

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Group3`



`Reserved1`



`Reserved2`



`UnitLength`



## Remarks
This structure holds data for the feature named "Time-Out" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that have this feature must respond to commands within a set time period. When these devices cannot complete commands in the allotted time, they complete the commands with an error.

When queried, devices supporting this feature must return the information indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>. No other feature-specific information is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>