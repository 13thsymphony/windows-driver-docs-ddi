---
UID: NS:ntddmmc._FEATURE_DATA_DISC_CONTROL_BLOCKS
title: "_FEATURE_DATA_DISC_CONTROL_BLOCKS"
author: windows-driver-content
description: The FEATURE_DATA_DISC_CONTROL_BLOCKS structure holds an array of the data reported for the Disc Control Block feature.
old-location: storage\feature_data_disc_control_blocks.htm
old-project: storage
ms.assetid: ed39e714-38c5-45cf-b1f0-dd00b4d49895
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PFEATURE_DATA_DISC_CONTROL_BLOCKS, FEATURE_DATA_DISC_CONTROL_BLOCKS, FEATURE_DATA_DISC_CONTROL_BLOCKS structure [Storage Devices], PFEATURE_DATA_DISC_CONTROL_BLOCKS, PFEATURE_DATA_DISC_CONTROL_BLOCKS structure pointer [Storage Devices], _FEATURE_DATA_DISC_CONTROL_BLOCKS, ntddmmc/FEATURE_DATA_DISC_CONTROL_BLOCKS, ntddmmc/PFEATURE_DATA_DISC_CONTROL_BLOCKS, storage.feature_data_disc_control_blocks, structs-CD-ROM_313fa292-b1c4-408d-94e9-491cb3d0aa0f.xml"
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
-	FEATURE_DATA_DISC_CONTROL_BLOCKS
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_DISC_CONTROL_BLOCKS, *PFEATURE_DATA_DISC_CONTROL_BLOCKS
---

# _FEATURE_DATA_DISC_CONTROL_BLOCKS structure
The FEATURE_DATA_DISC_CONTROL_BLOCKS structure holds an array of the data reported for the Disc Control Block feature.

## Syntax
````
typedef struct _FEATURE_DATA_DISC_CONTROL_BLOCKS {
  FEATURE_HEADER                      Header;
  FEATURE_DATA_DISC_CONTROL_BLOCKS_EX Data[];
} FEATURE_DATA_DISC_CONTROL_BLOCKS, *PFEATURE_DATA_DISC_CONTROL_BLOCKS;
````

## Members


`Data`

Contains zero, one, or more disk control blocks. Each disk control block is contained in a <a href="..\ntddmmc\ns-ntddmmc-_feature_data_disc_control_blocks_ex.md">FEATURE_DATA_DISC_CONTROL_BLOCKS_EX</a> structure.

`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

## Remarks
This structure holds data for the feature named "Disc Control Blocks" by the <i>SCSI Multimedia - 4 (MMC-4)</i> specification. Devices that support this feature can do reads and writes of disc control blocks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_feature_data_disc_control_blocks_ex.md">FEATURE_DATA_DISC_CONTROL_BLOCKS_EX</a>



<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_DISC_CONTROL_BLOCKS structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>