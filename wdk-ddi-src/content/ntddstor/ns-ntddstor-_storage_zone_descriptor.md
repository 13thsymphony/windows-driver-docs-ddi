---
UID: NS:ntddstor._STORAGE_ZONE_DESCRIPTOR
title: "_STORAGE_ZONE_DESCRIPTOR"
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\storage_zone_descriptor.htm
old-project: storage
ms.assetid: 33AE6D40-F54D-427D-B811-2188EA623A26
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PSTORAGE_ZONE_DESCRIPTOR, PSTORAGE_ZONE_DESCRIPTOR, PSTORAGE_ZONE_DESCRIPTOR structure pointer [Storage Devices], STORAGE_ZONE_DESCRIPTOR, STORAGE_ZONE_DESCRIPTOR structure [Storage Devices], _STORAGE_ZONE_DESCRIPTOR, ntddstor/PSTORAGE_ZONE_DESCRIPTOR, ntddstor/STORAGE_ZONE_DESCRIPTOR, storage.storage_zone_descriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddstor.h
req.include-header: 
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
-	ntddstor.h
api_name:
-	STORAGE_ZONE_DESCRIPTOR
product:
- Windows
targetos: Windows
req.typenames: STORAGE_ZONE_DESCRIPTOR, *PSTORAGE_ZONE_DESCRIPTOR
---

# _STORAGE_ZONE_DESCRIPTOR structure
<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>

## Syntax
```
typedef struct _STORAGE_ZONE_DESCRIPTOR {
  ULONG                  Size;
  STORAGE_ZONE_TYPES     ZoneType;
  STORAGE_ZONE_CONDITION ZoneCondition;
  BOOLEAN                ResetWritePointerRecommend;
  UCHAR                  Reserved0[3];
  ULONGLONG              ZoneSize;
  ULONGLONG              WritePointerOffset;
} STORAGE_ZONE_DESCRIPTOR, *PSTORAGE_ZONE_DESCRIPTOR;
```

## Members


`Size`

N/A

`ZoneType`

N/A

`ZoneCondition`



`ResetWritePointerRecommend`



`Reserved0`

N/A

`ZoneSize`

N/A

`WritePointerOffset`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddstor.h |