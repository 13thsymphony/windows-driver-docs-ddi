---
UID: NF.rilapi.RIL_GetIMSI
title: RIL_GetIMSI function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getimsi.htm
old-project: NetVista
ms.assetid: 2bc038bb-fe8a-4a22-b4e2-d6dcf2589a12
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RIL_GetIMSI
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
req.alt-api: RIL_GetIMSI
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

# RIL_GetIMSI function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_GetIMSI(
   HRIL     hRil,
   LPVOID   lpContext,
   HUICCAPP hUiccApp
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param hUiccApp 


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