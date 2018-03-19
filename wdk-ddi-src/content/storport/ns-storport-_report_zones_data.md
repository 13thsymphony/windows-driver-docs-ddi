---
UID: NS:storport._REPORT_ZONES_DATA
title: "_REPORT_ZONES_DATA"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\report_zones_data.htm
old-project: storage
ms.assetid: 67785cb0-388c-4348-b32a-99bcd02b7c04
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PREPORT_ZONES_DATA, PREPORT_ZONES_DATA, PREPORT_ZONES_DATA structure pointer [Storage Devices], REPORT_ZONES_DATA, REPORT_ZONES_DATA structure [Storage Devices], _REPORT_ZONES_DATA, scsi/PREPORT_ZONES_DATA, scsi/REPORT_ZONES_DATA, storage.report_zones_data"
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
-	REPORT_ZONES_DATA
product: Windows
targetos: Windows
req.typenames: REPORT_ZONES_DATA, *PREPORT_ZONES_DATA
req.product: Windows 10 or later.
---

# _REPORT_ZONES_DATA structure
<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>

## Syntax
````
typedef struct _REPORT_ZONES_DATA {
  UCHAR            ZoneListLength[4];
  UCHAR            Same  :4;
  UCHAR            Reserved1  :4;
  UCHAR            Reserved2[4];
  UCHAR            MaxLBA[8];
  UCHAR            Reserved3[48];
#ifndef (__midl)
  ZONE_DESCRIPTIOR ZoneDescriptors[ANYSIZE_ARRAY];
#endif 
} REPORT_ZONES_DATA, *PREPORT_ZONES_DATA;
````

## Members


`ZoneListLength`

N/A

`Same`

N/A

`Reserved1`

N/A

`Reserved2`

N/A

`MaxLBA`

N/A

`Reserved3`

N/A

`ZoneDescriptors`

N/A


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | storport.h (include Minitape.h, Storport.h) |