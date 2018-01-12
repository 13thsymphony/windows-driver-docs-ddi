---
UID: NF:rilapi.RIL_SendMsg
title: RIL_SendMsg function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_sendmsg.htm
old-project: netvista
ms.assetid: 0ae1ed49-af07-4e34-80fa-34a55c973cfb
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RIL_SendMsg
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
req.alt-api: RIL_SendMsg
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
req.typenames: RH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER, *PRH_QUERY_CONNECTION_PROPERTIES_OUTPUT_BUFFER
req.product: Windows 10 or later.
---

# RIL_SendMsg function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            



## -syntax

````
HRESULT  RIL_SendMsg(
   HRIL              hRil,
   LPVOID            lpContext,
   DWORD             dwExecutor,
   HUICCAPP          hUiccApp,
   const RILMESSAGE  lpMessage,
   DWORD             dwOptions
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param dwExecutor 


### -param hUiccApp 


### -param lpMessage 


### -param dwOptions 


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