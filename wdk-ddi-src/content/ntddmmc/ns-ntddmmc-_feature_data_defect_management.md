---
UID: NS:ntddmmc._FEATURE_DATA_DEFECT_MANAGEMENT
title: "_FEATURE_DATA_DEFECT_MANAGEMENT"
author: windows-driver-content
description: The FEATURE_DATA_DEFECT_MANAGEMENT structure contains information for the Defect Management feature.
old-location: storage\feature_data_defect_management.htm
old-project: storage
ms.assetid: ff032dbd-8c84-4442-bbd5-a27b61617d47
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PFEATURE_DATA_DEFECT_MANAGEMENT, FEATURE_DATA_DEFECT_MANAGEMENT, FEATURE_DATA_DEFECT_MANAGEMENT structure [Storage Devices], PFEATURE_DATA_DEFECT_MANAGEMENT, PFEATURE_DATA_DEFECT_MANAGEMENT structure pointer [Storage Devices], _FEATURE_DATA_DEFECT_MANAGEMENT, ntddmmc/FEATURE_DATA_DEFECT_MANAGEMENT, ntddmmc/PFEATURE_DATA_DEFECT_MANAGEMENT, storage.feature_data_defect_management, structs-CD-ROM_3c73a6a8-5a76-4a73-b3fa-cae137659fad.xml"
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
-	FEATURE_DATA_DEFECT_MANAGEMENT
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_DEFECT_MANAGEMENT, *PFEATURE_DATA_DEFECT_MANAGEMENT
---

# _FEATURE_DATA_DEFECT_MANAGEMENT structure
The FEATURE_DATA_DEFECT_MANAGEMENT structure contains information for the Defect Management feature.

## Syntax
```
typedef struct _FEATURE_DATA_DEFECT_MANAGEMENT {
  FEATURE_HEADER Header;
  UCHAR  : 7     Reserved1;
  UCHAR  : 1     SupplimentalSpareArea;
  UCHAR          Reserved2[3];
} *PFEATURE_DATA_DEFECT_MANAGEMENT, FEATURE_DATA_DEFECT_MANAGEMENT;
```

## Members


`Header`

Contains a <a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Reserved1`

Reserved.

`SupplimentalSpareArea`

Indicates, when set to 1, that the logical unit supports the READ DVD STRUCTURE command with a format code of 0Ah. See the <i>SCSI Multimedia - 4 (MMC-4)</i> specification for more information.

`Reserved2`

Reserved.

## Remarks
This structure holds data for the feature named "Defect Management" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature are able to provide contiguous address space that is guaranteed to be defect free.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553848">FEATURE_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553850">FEATURE_NUMBER</a>