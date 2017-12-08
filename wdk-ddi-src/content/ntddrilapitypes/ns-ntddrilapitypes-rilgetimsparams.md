---
UID: NS.NTDDRILAPITYPES.RILGETIMSPARAMS
title: RILGETIMSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetimsparams.htm
old-project: netvista
ms.assetid: 4e8f01af-9279-483a-90f9-d0391122ba5b
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILGETIMSPARAMS, RILGETIMSPARAMS, *LPRILGETIMSPARAMS
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
req.alt-api: RILGETIMSPARAMS
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

# RILGETIMSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILGETIMSPARAMS {
  DWORD  cbSize;
  DWORD  dwExecutor;
} RILGETIMSPARAMS, RILGETIMSPARAMS;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


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