---
UID: NS:ntddstor._STORAGE_ZONE_DESCRIPTOR
title: _STORAGE_ZONE_DESCRIPTOR
author: windows-driver-content
description: Note  This structure is for internal use only and should not be called from your code. .
old-location: storage\storage_zone_descriptor.htm
old-project: storage
ms.assetid: 33AE6D40-F54D-427D-B811-2188EA623A26
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: _STORAGE_ZONE_DESCRIPTOR, STORAGE_ZONE_DESCRIPTOR, *PSTORAGE_ZONE_DESCRIPTOR
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
req.alt-api: STORAGE_ZONE_DESCRIPTOR
req.alt-loc: ntddstor.h
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
req.typenames: STORAGE_ZONE_DESCRIPTOR, *PSTORAGE_ZONE_DESCRIPTOR
---

# _STORAGE_ZONE_DESCRIPTOR structure



## -description

<div class="alert"><b>Note</b>  This  structure is for internal use only and should not be called from your code.</div>
<div> </div>




## -syntax

````
typedef struct _STORAGE_ZONE_DESCRIPTOR {
  ULONG                  Size;
  STORAGE_ZONE_TYPES     ZoneType;
  STORAGE_ZONE_CONDITION ResetWritePointerRecomend;
  BOOLEAN                ResetWritePointerRecomend;
                         Reserved0[3];
  ULONGLONG              ZoneSize;
  ULONGLONG              WriterPointerOffset;
} STORAGE_ZONE_DESCRIPTOR, *PSTORAGE_ZONE_DESCRIPTOR;
````


## -struct-fields

### -field Size

N/A


### -field ZoneType

N/A


### -field ResetWritePointerRecomend

N/A


### -field ResetWritePointerRecomend

N/A


### -field Reserved0

N/A


### -field ZoneSize

N/A


### -field WriterPointerOffset

N/A


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddstor.h</dt>
</dl>
</td>
</tr>
</table>