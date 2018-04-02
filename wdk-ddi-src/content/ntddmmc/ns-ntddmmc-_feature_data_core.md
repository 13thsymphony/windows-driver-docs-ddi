---
UID: NS:ntddmmc._FEATURE_DATA_CORE
title: "_FEATURE_DATA_CORE"
author: windows-driver-content
description: The FEATURE_DATA_CORE structure holds data for the Core feature descriptor.
old-location: storage\feature_data_core.htm
old-project: storage
ms.assetid: cd8e989a-1030-4f37-bb39-38974764ccb2
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_CORE, FEATURE_DATA_CORE, FEATURE_DATA_CORE structure [Storage Devices], PFEATURE_DATA_CORE, PFEATURE_DATA_CORE structure pointer [Storage Devices], _FEATURE_DATA_CORE, ntddmmc/FEATURE_DATA_CORE, ntddmmc/PFEATURE_DATA_CORE, storage.feature_data_core, structs-CD-ROM_1b2608f2-398d-4733-b319-a92d932504e7.xml"
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
-	FEATURE_DATA_CORE
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_CORE, *PFEATURE_DATA_CORE
---

# _FEATURE_DATA_CORE structure
The FEATURE_DATA_CORE structure holds data for the Core feature descriptor.

## Syntax
```
typedef struct _FEATURE_DATA_CORE {
  FEATURE_HEADER Header;
  UCHAR          PhysicalInterface[4];
  UCHAR  : 1     DeviceBusyEvent;
  UCHAR  : 1     INQUIRY2;
  UCHAR  : 6     Reserved1;
  UCHAR          Reserved2[3];
} *PFEATURE_DATA_CORE, FEATURE_DATA_CORE;
```

## Members


`Header`

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`PhysicalInterface`

Must be set to the current communication path between initiator and device, as defined in the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. The bytes of this array are arranged in big-endian order. <b>PhysicalInterface</b>[0] contains the most significant byte, and <b>PhysicalInterface</b>[3] contains the least significant byte.

`DeviceBusyEvent`



`INQUIRY2`



`Reserved1`



`Reserved2`



## Remarks
Indicates the feature named "Core" by the <i>MMC-3 </i>specification. This feature encompasses the basic functionality which is mandatory for all devices that support the <i>MMC-3</i> standard. See the <i>MMC-3</i> specification for a description of the capabilities included in the Core feature.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>