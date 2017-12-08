---
UID: NF.rilapi.RIL_EnumerateSlots
title: RIL_EnumerateSlots function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_enumerateslots.htm
old-project: netvista
ms.assetid: 58df87d5-1e7b-4ec8-8e88-631bbd78757a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RIL_EnumerateSlots
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rilapi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RIL_EnumerateSlots
req.alt-loc: rilapi.h
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

# RIL_EnumerateSlots function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax

````
HRESULT  RIL_EnumerateSlots(
   HRIL   hRil,
   LPVOID lpContext
);
````


## -parameters

### -param hRil 


### -param lpContext 


## -returns
If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Rilapi.h</dt>
</dl>
</td>
</tr>
</table>