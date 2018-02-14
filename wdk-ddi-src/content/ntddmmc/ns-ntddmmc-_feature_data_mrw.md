---
UID: NS:ntddmmc._FEATURE_DATA_MRW
title: "_FEATURE_DATA_MRW"
author: windows-driver-content
description: The FEATURE_DATA_MRW structure contains information about the MRW feature.
old-location: storage\feature_data_mrw.htm
old-project: storage
ms.assetid: af0c8c50-c5a0-4395-a608-fced6ac3cfe5
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storage.feature_data_mrw, ntddmmc/FEATURE_DATA_MRW, PFEATURE_DATA_MRW, PFEATURE_DATA_MRW structure pointer [Storage Devices], ntddmmc/PFEATURE_DATA_MRW, structs-CD-ROM_54208a52-0bc2-4e97-a3b1-4d57f5192ce4.xml, FEATURE_DATA_MRW, *PFEATURE_DATA_MRW, FEATURE_DATA_MRW structure [Storage Devices], _FEATURE_DATA_MRW
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddmmc.h
apiname:
-	FEATURE_DATA_MRW
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_MRW, *PFEATURE_DATA_MRW
---

# _FEATURE_DATA_MRW structure
The FEATURE_DATA_MRW structure contains information about the MRW feature.

## Syntax
````
typedef struct _FEATURE_DATA_MRW {
  FEATURE_HEADER Header;
  UCHAR          Write  :1;
  UCHAR          DvdPlusRead  :1;
  UCHAR          DvdPlusWrite  :1;
  UCHAR          Reserved01  :5;
  UCHAR          Reserved2[3];
} FEATURE_DATA_MRW, *PFEATURE_DATA_MRW;
````

## Members


`DvdPlusRead`



`DvdPlusWrite`



`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`Reserved01`



`Reserved2`

Reserved.

`Write`

Indicates, if set to 1, that the device can format discs using the MRW format and write to discs that have been formatted in this manner. See the <i>SCSI Multimedia - 4 (MMC-4)</i> specification for more information.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_MRW structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>