---
UID: NS:storport._ZONE_DESCRIPTIOR
title: "_ZONE_DESCRIPTIOR"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\zone_descriptior.htm
old-project: storage
ms.assetid: 8326f683-3952-486e-b322-80ce96759366
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PZONE_DESCRIPTIOR, PZONE_DESCRIPTIOR, PZONE_DESCRIPTIOR structure pointer [Storage Devices], ZONE_DESCRIPTIOR, ZONE_DESCRIPTIOR structure [Storage Devices], _ZONE_DESCRIPTIOR, scsi/PZONE_DESCRIPTIOR, scsi/ZONE_DESCRIPTIOR, storage.zone_descriptior"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: storport.h
req.include-header: Minitape.h, Storport.h
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
-	scsi.h
api_name:
-	ZONE_DESCRIPTIOR
product: Windows
targetos: Windows
req.typenames: ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR
req.product: Windows 10 or later.
---

# _ZONE_DESCRIPTIOR structure
<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>

## Syntax
````
typedef struct _ZONE_DESCRIPTIOR {
  UCHAR      ZoneType  :4;
  UCHAR      Reserved1  :4;
  UCHAR  : 1 Reset  :1;
  UCHAR      Non_Seq  :1;
  UCHAR      Reserved2  :2;
  UCHAR      ZoneCondition  :4;
  UCHAR      Reserved3[6];
  UCHAR      ZoneLength[8];
  UCHAR      ZoneStartLBA[8];
  UCHAR      WritePointerLBA[8];
  UCHAR      Reserved4[32];
} ZONE_DESCRIPTIOR, *PZONE_DESCRIPTIOR;
````

## Members


`ZoneType`

N/A

`Reserved1`

N/A

`Reset`

N/A

`Non_Seq`

N/A

`Reserved2`

N/A

`ZoneCondition`

N/A

`Reserved3`

N/A

`ZoneLength`

N/A

`ZoneStartLBA`

N/A

`WritePointerLBA`

N/A

`Reserved4`

N/A


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | storport.h (include Minitape.h, Storport.h) |