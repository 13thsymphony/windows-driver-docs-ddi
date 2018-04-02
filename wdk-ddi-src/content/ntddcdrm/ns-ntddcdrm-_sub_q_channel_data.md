---
UID: NS:ntddcdrm._SUB_Q_CHANNEL_DATA
title: "_SUB_Q_CHANNEL_DATA"
author: windows-driver-content
description: Device control IRPs with a control code of IOCTL_CDROM_READ_Q_CHANNEL return their output data in this union.
old-location: storage\sub_q_channel_data.htm
old-project: storage
ms.assetid: d0304ac7-cb19-499c-81af-98be33312951
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSUB_Q_CHANNEL_DATA, PSUB_Q_CHANNEL_DATA, PSUB_Q_CHANNEL_DATA union pointer [Storage Devices], SUB_Q_CHANNEL_DATA, SUB_Q_CHANNEL_DATA union [Storage Devices], _SUB_Q_CHANNEL_DATA, ntddcdrm/PSUB_Q_CHANNEL_DATA, ntddcdrm/SUB_Q_CHANNEL_DATA, storage.sub_q_channel_data, structs-CD-ROM_f35761c8-b362-48eb-9cfa-6ee5e7232411.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddcdrm.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddcdrm.h
api_name:
-	SUB_Q_CHANNEL_DATA
product: Windows
targetos: Windows
req.typenames: SUB_Q_CHANNEL_DATA, *PSUB_Q_CHANNEL_DATA
---

# _SUB_Q_CHANNEL_DATA structure
Device control IRPs with a control code of IOCTL_CDROM_READ_Q_CHANNEL return their output data in this union.

## Syntax
```
typedef struct _SUB_Q_CHANNEL_DATA {
  SUB_Q_CURRENT_POSITION     CurrentPosition;
  SUB_Q_MEDIA_CATALOG_NUMBER MediaCatalog;
  SUB_Q_TRACK_ISRC           TrackIsrc;
} *PSUB_Q_CHANNEL_DATA, SUB_Q_CHANNEL_DATA;
```

## Members


`CurrentPosition`

Contains position information, such as the absolute and relative addresses, in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567596">SUB_Q_CURRENT_POSITION</a> structure.

`MediaCatalog`

Contains the media catalog number in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567600">SUB_Q_MEDIA_CATALOG_NUMBER</a>  structure.

`TrackIsrc`

Contains the TrackIsrc code in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff567601">SUB_Q_TRACK_ISRC</a> structure.

## Remarks
The value of the <b>Format </b>member of the CDROM_SUB_Q_DATA_FORMAT structure that is passed as input with IOCTL_CDROM_READ_Q_CHANNEL determines which member of this union is used to return the output data. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff551371">CDROM_SUB_Q_DATA_FORMAT</a> for a detailed explanation.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddcdrm.h (include Ntddcdrm.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551371">CDROM_SUB_Q_DATA_FORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559363">IOCTL_CDROM_READ_Q_CHANNEL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567596">SUB_Q_CURRENT_POSITION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567600">SUB_Q_MEDIA_CATALOG_NUMBER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567601">SUB_Q_TRACK_ISRC</a>