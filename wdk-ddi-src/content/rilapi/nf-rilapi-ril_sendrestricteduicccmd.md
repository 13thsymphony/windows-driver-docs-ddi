---
UID: NF.rilapi.RIL_SendRestrictedUiccCmd
title: RIL_SendRestrictedUiccCmd function
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril_sendrestricteduicccmd.htm
old-project: netvista
ms.assetid: f9341659-105b-4ec7-bce7-878698de8c14
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RIL_SendRestrictedUiccCmd
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
req.alt-api: RIL_SendRestrictedUiccCmd
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

# RIL_SendRestrictedUiccCmd function



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 

            


## -syntax

````
HRESULT  RIL_SendRestrictedUiccCmd(
   HRIL                         hRil,
   LPVOID                       lpContext,
   RILUICCCOMMAND               dwCommand,
   const RILUICCCMDPARAMETERS   lpParameters,
   const BYTE                   lpbData,
   DWORD                        dwSize,
   const RILUICCLOCKCREDENTIAL  lpLockVerification
);
````


## -parameters

### -param hRil 


### -param lpContext 


### -param dwCommand 


### -param lpParameters 


### -param lpbData 


### -param dwSize 


### -param lpLockVerification 


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