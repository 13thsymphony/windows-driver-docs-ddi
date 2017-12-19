---
UID: NS.NTDDRILAPITYPES.RILRTTDATA
title: RILRTTDATA
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrttdata.htm
old-project: NetVista
ms.assetid: 037831c7-d0ef-4cbc-a414-a77010e228a5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILRTTDATA, LPRILRTTDATA, RILRTTDATA, *LPRILRTTDATA
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
req.alt-api: RILRTTDATA
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

# RILRTTDATA structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILRTTDATA {
  DWORD       cbSize;
  DWORD       dwID;
  DWORD       dwExecutor;
  WCHAR [127] wszRTTData;
} RILRTTDATA, RILRTTDATA;
````


## -struct-fields

### -field cbSize


### -field dwID


### -field dwExecutor


### -field wszRTTData


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