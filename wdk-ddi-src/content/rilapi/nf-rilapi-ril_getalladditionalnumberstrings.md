---
UID: NF.rilapi.RIL_GetAllAdditionalNumberStrings
title: RIL_GetAllAdditionalNumberStrings function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_getalladditionalnumberstrings.htm
old-project: netvista
ms.assetid: fc0f5a3b-3ab0-4103-85a2-f7b5ce64ec79
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RIL_GetAllAdditionalNumberStrings
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
req.alt-api: RIL_GetAllAdditionalNumberStrings
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

# RIL_GetAllAdditionalNumberStrings function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_GetAllAdditionalNumberStrings(
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