---
UID: NS.NTDDRILAPITYPES.RILSYSTEMTIME
title: RILSYSTEMTIME
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemtime.htm
old-project: netvista
ms.assetid: da01963f-a0eb-4222-b0c7-20b924f65f66
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILSYSTEMTIME, *LPRILSYSTEMTIME, RILSYSTEMTIME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSYSTEMTIME
req.alt-loc: ntddrilapitypes.h
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
---

# RILSYSTEMTIME structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILSYSTEMTIME {
  WORD  wYear;
  WORD  wMonth;
  WORD  wDayOfWeek;
  WORD  wDay;
  WORD  wHour;
  WORD  wMinute;
  WORD  wSecond;
  WORD  wMilliseconds;
} RILSYSTEMTIME, RILSYSTEMTIME;
````


## -struct-fields

### -field wYear


### -field wMonth


### -field wDayOfWeek


### -field wDay


### -field wHour


### -field wMinute


### -field wSecond


### -field wMilliseconds


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>