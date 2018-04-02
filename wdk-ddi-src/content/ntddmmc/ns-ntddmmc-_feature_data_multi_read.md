---
UID: NS:ntddmmc._FEATURE_DATA_MULTI_READ
title: "_FEATURE_DATA_MULTI_READ"
author: windows-driver-content
description: The FEATURE_DATA_MULTI_READ structure contains data for the multiread feature.
old-location: storage\feature_data_multi_read.htm
old-project: storage
ms.assetid: a7db6bd2-7c04-4bfc-b4b4-db1f99520e56
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_MULTI_READ, FEATURE_DATA_MULTI_READ, FEATURE_DATA_MULTI_READ structure [Storage Devices], PFEATURE_DATA_MULTI_READ, PFEATURE_DATA_MULTI_READ structure pointer [Storage Devices], _FEATURE_DATA_MULTI_READ, ntddmmc/FEATURE_DATA_MULTI_READ, ntddmmc/PFEATURE_DATA_MULTI_READ, storage.feature_data_multi_read, structs-CD-ROM_687fe1cb-1667-4650-97c5-d6e4af7df2af.xml"
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
-	FEATURE_DATA_MULTI_READ
product:
- Windows
targetos: Windows
req.typenames: FEATURE_DATA_MULTI_READ, *PFEATURE_DATA_MULTI_READ
---

# _FEATURE_DATA_MULTI_READ structure
The FEATURE_DATA_MULTI_READ structure contains data for the multiread feature.

## Syntax
```
typedef struct _FEATURE_DATA_MULTI_READ {
  FEATURE_HEADER Header;
} *PFEATURE_DATA_MULTI_READ, FEATURE_DATA_MULTI_READ;
```

## Members


`Header`

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor.

## Remarks
This structure holds data for the feature named "MultiRead," originally defined by the Optical Storage Technology Association (OSTA) and incorporated into the <i>MMC-3 </i>specification. Devices that support this feature can read all CD media types. 

When queried, devices supporting this feature must return the information indicated in <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>. No other feature-specific information is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>