---
UID: NS.RILAPITYPES.RILNETWORKCODE~R1
title: RILNETWORKCODE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilnetworkcode_2.htm
old-project: netvista
ms.assetid: 13d5914e-b42f-41ce-b86b-b7d638244558
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILNETWORKCODE, RILNETWORKCODE, *LPRILNETWORKCODE
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
req.alt-api: RILNETWORKCODE
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

# RILNETWORKCODE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef struct _RILNETWORKCODE {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwExecutor;
  DWORD  dwMCC;
  DWORD  dwMNC;
  DWORD  dwSID;
  DWORD  dwNID;
  DWORD  dwRI;
} RILNETWORKCODE, RILNETWORKCODE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwMCC


### -field dwMNC


### -field dwSID


### -field dwNID


### -field dwRI


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