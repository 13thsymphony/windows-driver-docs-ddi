---
UID: NS:ntddmmc._FEATURE_DATA_RESERVED
title: "_FEATURE_DATA_RESERVED"
author: windows-driver-content
description: The FEATURE_DATA_RESERVED structure holds information about an unspecified feature.
old-location: storage\feature_data_reserved.htm
old-project: storage
ms.assetid: 686bc6e0-7455-4b86-93ce-09b7c7d60240
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_RESERVED, FEATURE_DATA_RESERVED, FEATURE_DATA_RESERVED structure [Storage Devices], PFEATURE_DATA_RESERVED, PFEATURE_DATA_RESERVED structure pointer [Storage Devices], _FEATURE_DATA_RESERVED, ntddmmc/FEATURE_DATA_RESERVED, ntddmmc/PFEATURE_DATA_RESERVED, storage.feature_data_reserved, structs-CD-ROM_4fc9f24f-2488-493d-8e63-2e4c8a3ab879.xml"
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
-	FEATURE_DATA_RESERVED
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_RESERVED, *PFEATURE_DATA_RESERVED
---

# _FEATURE_DATA_RESERVED structure
The FEATURE_DATA_RESERVED structure holds information about an unspecified feature.

## Syntax
````
typedef struct _FEATURE_DATA_RESERVED {
  FEATURE_HEADER Header;
  UCHAR          Data[];
} FEATURE_DATA_RESERVED, *PFEATURE_DATA_RESERVED;
````

## Members


`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Data`

Contains an array describing unspecified feature structure members.

## Remarks
You can use this structure to access the data of any feature structure as though it were a simple character array.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>