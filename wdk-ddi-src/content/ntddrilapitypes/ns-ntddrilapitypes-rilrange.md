---
UID: NS.ntddrilapitypes.RILRANGE
title: RILRANGE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrange.htm
old-project: netvista
ms.assetid: 2f704899-eb5e-4632-a76d-eb474f3273f9
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILRANGE, RILRANGE, *LPRILRANGE
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
req.alt-api: RILRANGE
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
req.iface: 
---

# RILRANGE structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILRANGE {
  DWORD  dwMinValue;
  DWORD  dwMaxValue;
} RILRANGE, RILRANGE;
````


## -struct-fields
<dl>

### -field dwMinValue

<dd></dd>

### -field dwMaxValue

<dd></dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>