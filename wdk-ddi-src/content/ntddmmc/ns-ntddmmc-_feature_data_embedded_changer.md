---
UID: NS:ntddmmc._FEATURE_DATA_EMBEDDED_CHANGER
title: "_FEATURE_DATA_EMBEDDED_CHANGER"
author: windows-driver-content
description: The FEATURE_DATA_EMBEDDED_CHANGER structure holds data for the Embedded Changer feature.
old-location: storage\feature_data_embedded_changer.htm
old-project: storage
ms.assetid: 1335d1fa-af96-4a31-a1cf-266f7a3325ef
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_EMBEDDED_CHANGER, FEATURE_DATA_EMBEDDED_CHANGER, FEATURE_DATA_EMBEDDED_CHANGER structure [Storage Devices], PFEATURE_DATA_EMBEDDED_CHANGER, PFEATURE_DATA_EMBEDDED_CHANGER structure pointer [Storage Devices], _FEATURE_DATA_EMBEDDED_CHANGER, ntddmmc/FEATURE_DATA_EMBEDDED_CHANGER, ntddmmc/PFEATURE_DATA_EMBEDDED_CHANGER, storage.feature_data_embedded_changer, structs-CD-ROM_655edb8d-6748-4d10-8cd9-51b3a696bccd.xml"
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
-	FEATURE_DATA_EMBEDDED_CHANGER
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_EMBEDDED_CHANGER, *PFEATURE_DATA_EMBEDDED_CHANGER
---

# _FEATURE_DATA_EMBEDDED_CHANGER structure
The FEATURE_DATA_EMBEDDED_CHANGER structure holds data for the Embedded Changer feature.

## Syntax
```
typedef struct _FEATURE_DATA_EMBEDDED_CHANGER {
  FEATURE_HEADER Header;
  UCHAR  : 2     Reserved1;
  UCHAR  : 1     SupportsDiscPresent;
  UCHAR  : 1     Reserved2;
  UCHAR  : 1     SideChangeCapable;
  UCHAR  : 3     Reserved3;
  UCHAR          Reserved4[2];
  UCHAR  : 5     HighestSlotNumber;
  UCHAR  : 3     Reserved;
} *PFEATURE_DATA_EMBEDDED_CHANGER, FEATURE_DATA_EMBEDDED_CHANGER;
```

## Members


`Header`

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Reserved1`

Reserved.

`SupportsDiscPresent`

Indicates, when set to 1, that the device can report the contents of the slots after a reset or magazine change. When set to zero, this bit indicates that the device can report the contents of the slots after reset or magazine change.

`Reserved2`

Reserved.

`SideChangeCapable`

Indicates, when set to 1, that the device is capable of selecting both sides of the media. When set to zero, this bit indicates that the device is not capable of selecting both sides of the media.

`Reserved3`

Reserved.

`Reserved4`

Reserved.

`HighestSlotNumber`

Indicates the number of slots minus 1.

`Reserved`

Reserved.

## Remarks
This structure holds data for the feature named "Embedded Changer" by the <i>SCSI Multimedia - 4 (MMC-4) </i>specification. Devices that support this feature can move media back and forth between a media storage area and the mechanism that actually accesses the media.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>