---
UID: NS:ntddmmc._FEATURE_DATA_DEFECT_MANAGEMENT
title: "_FEATURE_DATA_DEFECT_MANAGEMENT"
author: windows-driver-content
description: The FEATURE_DATA_DEFECT_MANAGEMENT structure contains information for the Defect Management feature.
old-location: storage\feature_data_defect_management.htm
old-project: storage
ms.assetid: ff032dbd-8c84-4442-bbd5-a27b61617d47
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
````
typedef struct _FEATURE_DATA_DEFECT_MANAGEMENT {
  FEATURE_HEADER Header;
  UCHAR          Reserved1  :7;
  UCHAR          SupplimentalSpareArea  :1;
  UCHAR          Reserved2[3];
} FEATURE_DATA_DEFECT_MANAGEMENT, *PFEATURE_DATA_DEFECT_MANAGEMENT;
````

## Members


`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Reserved1`

Reserved.

`Reserved2`

Reserved.

`SupplimentalSpareArea`

Indicates, when set to 1, that the logical unit supports the READ DVD STRUCTURE command with a format code of 0Ah. See the <i>SCSI Multimedia - 4 (MMC-4)</i> specification for more information.

## Remarks
This structure holds data for the feature named "Defect Management" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature are able to provide contiguous address space that is guaranteed to be defect free.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DEFECT_MANAGEMENT structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>