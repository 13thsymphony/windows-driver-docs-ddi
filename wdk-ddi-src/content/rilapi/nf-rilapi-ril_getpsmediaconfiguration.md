---
UID: NF.rilapi.RIL_GetPSMediaConfiguration
title: RIL_GetPSMediaConfiguration function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getpsmediaconfiguration.htm
old-project: netvista
ms.assetid: f7b1f2a6-d57a-44ec-b14b-8b41b020935e
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RIL_GetPSMediaConfiguration
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
req.alt-api: RIL_GetPSMediaConfiguration
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

# RIL_GetPSMediaConfiguration function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax

````
HRESULT  RIL_GetPSMediaConfiguration(
   HRIL   hRil,
   LPVOID lpContext,
   DWORD  dwExecutor
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param dwExecutor 


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