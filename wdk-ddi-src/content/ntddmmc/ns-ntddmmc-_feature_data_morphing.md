---
UID: NS:ntddmmc._FEATURE_DATA_MORPHING
title: "_FEATURE_DATA_MORPHING"
author: windows-driver-content
description: The FEATURE_DATA_MORPHING structure contains information about the morphing feature.
old-location: storage\feature_data_morphing.htm
old-project: storage
ms.assetid: b3eaabdf-0163-4679-9b22-d8ec53abed59
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PFEATURE_DATA_MORPHING, FEATURE_DATA_MORPHING, FEATURE_DATA_MORPHING structure [Storage Devices], PFEATURE_DATA_MORPHING, PFEATURE_DATA_MORPHING structure pointer [Storage Devices], _FEATURE_DATA_MORPHING, ntddmmc/FEATURE_DATA_MORPHING, ntddmmc/PFEATURE_DATA_MORPHING, storage.feature_data_morphing, structs-CD-ROM_f159fbd8-73db-440b-a4f3-2429181c6836.xml"
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
-	FEATURE_DATA_MORPHING
product: Windows
targetos: Windows
req.typenames: FEATURE_DATA_MORPHING, *PFEATURE_DATA_MORPHING
---

# _FEATURE_DATA_MORPHING structure
The FEATURE_DATA_MORPHING structure contains information about the morphing feature.

## Syntax
````
typedef struct _FEATURE_DATA_MORPHING {
  FEATURE_HEADER Header;
  UCHAR          Asynchronous  :1;
  UCHAR          OCEvent  :1;
  UCHAR          Reserved01  :6;
  UCHAR          Reserved2[3];
} FEATURE_DATA_MORPHING, *PFEATURE_DATA_MORPHING;
````

## Members


`Asynchronous`

Indicates, when set to 1, that the initiator can request device status asynchronously. If set to zero, the initiator must use polling to request status.

`Header`

Contains a <a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a> structure with header information for this feature descriptor.

`OCEvent`



`Reserved01`



`Reserved2`

Reserved.

## Remarks
This structure holds data for the feature named "Morphing" by the <i>MMC-3 </i>specification. Devices that support this feature can notify the initiator of operational changes and allow the initiator to prevent operational changes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddmmc.h (include Ntddcdrm.h) |

## See Also

<a href="..\ntddmmc\ns-ntddmmc-_feature_header.md">FEATURE_HEADER</a>



<a href="..\ntddmmc\ne-ntddmmc-_feature_number.md">FEATURE_NUMBER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20FEATURE_DATA_MORPHING structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>