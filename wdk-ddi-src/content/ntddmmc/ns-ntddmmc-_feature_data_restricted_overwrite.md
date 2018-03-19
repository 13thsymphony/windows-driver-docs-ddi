---
UID: NS:ntddmmc._FEATURE_DATA_RESTRICTED_OVERWRITE
title: "_FEATURE_DATA_RESTRICTED_OVERWRITE"
author: windows-driver-content
description: The FEATURE_DATA_RESTRICTED_OVERWRITE structure holds information about the Restricted Overwrite feature.
old-location: storage\feature_data_restricted_overwrite.htm
old-project: storage
ms.assetid: d9f3e892-1ed5-4030-a656-7d2d294b1c82
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_RESTRICTED_OVERWRITE, FEATURE_DATA_RESTRICTED_OVERWRITE, FEATURE_DATA_RESTRICTED_OVERWRITE structure [Storage Devices], PFEATURE_DATA_RESTRICTED_OVERWRITE, PFEATURE_DATA_RESTRICTED_OVERWRITE structure pointer [Storage Devices], _FEATURE_DATA_RESTRICTED_OVERWRITE, ntddmmc/FEATURE_DATA_RESTRICTED_OVERWRITE, ntddmmc/PFEATURE_DATA_RESTRICTED_OVERWRITE, storage.feature_data_restricted_overwrite, structs-CD-ROM_d2d9725b-16c9-4361-a2fc-90bdc2d7905c.xml"
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
-	FEATURE_DATA_RESTRICTED_OVERWRITE
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_RESTRICTED_OVERWRITE, *PFEATURE_DATA_RESTRICTED_OVERWRITE
---

# _FEATURE_DATA_RESTRICTED_OVERWRITE structure
The FEATURE_DATA_RESTRICTED_OVERWRITE structure holds information about the Restricted Overwrite feature.

## Syntax
````
typedef struct _FEATURE_DATA_RESTRICTED_OVERWRITE {
  FEATURE_HEADER Header;
} FEATURE_DATA_RESTRICTED_OVERWRITE, *PFEATURE_DATA_RESTRICTED_OVERWRITE;
````

## Members


`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

## Remarks
This structure holds data for the feature named "Restricted Overwrite" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can only overwrite a limited set of logical blocks at any given time. 

When queried, devices supporting this feature must return the information indicated in <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>. No other feature-specific information is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>