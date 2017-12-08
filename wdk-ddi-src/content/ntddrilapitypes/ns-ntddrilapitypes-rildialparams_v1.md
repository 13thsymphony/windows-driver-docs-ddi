---
UID: NS.NTDDRILAPITYPES.RILDIALPARAMS_V1
title: RILDIALPARAMS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildialparams_v1.htm
old-project: netvista
ms.assetid: e424808a-8389-43ff-9cd4-cf2668f8d2a3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILDIALPARAMS_V1, *LPRILDIALPARAMS_V1, RILDIALPARAMS_V1
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
req.alt-api: RILDIALPARAMS_V1
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

# RILDIALPARAMS_V1 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILDIALPARAMS_V1 {
  DWORD       dwExecutor;
  RILADDRESS  raAddress;
  DWORD       dwOptions;
} RILDIALPARAMS_V1, RILDIALPARAMS_V1;
````


## -struct-fields

### -field dwExecutor


### -field raAddress


### -field dwOptions


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