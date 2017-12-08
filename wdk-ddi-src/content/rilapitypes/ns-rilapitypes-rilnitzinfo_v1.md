---
UID: NS.RILAPITYPES.RILNITZINFO_V1
title: RILNITZINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnitzinfo_v1_2.htm
old-project: netvista
ms.assetid: ded74c48-b9a8-4ee4-8df9-3dc99892d41d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILNITZINFO_V1, *LPRILNITZINFO_V1, RILNITZINFO_V1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILNITZINFO_V1
req.alt-loc: rilapitypes.h
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
req.product: Windows 10 or later.
---

# RILNITZINFO_V1 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef struct _RILNITZINFO_V1 {
  DWORD          cbSize;
  DWORD          dwParams;
  DWORD          dwExecutor;
  int            TimeZoneOffsetMinutes;
  int            DaylightSavingOffsetMinutes;
  RILSYSTEMTIME  SysTime;
} RILNITZINFO_V1, RILNITZINFO_V1;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field TimeZoneOffsetMinutes


### -field DaylightSavingOffsetMinutes


### -field SysTime


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Rilapitypes.h</dt>
</dl>
</td>
</tr>
</table>