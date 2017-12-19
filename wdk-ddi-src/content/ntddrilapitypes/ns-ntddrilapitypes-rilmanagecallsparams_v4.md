---
UID: NS.NTDDRILAPITYPES.RILMANAGECALLSPARAMS_V4
title: RILMANAGECALLSPARAMS_V4
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallsparams_v4.htm
old-project: NetVista
ms.assetid: 8e38c6d5-bd61-455e-a628-b4e6ef9c936c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILMANAGECALLSPARAMS_V4, *LPRILMANAGECALLSPARAMS, LPRILMANAGECALLSPARAMS, LPRILMANAGECALLSPARAMS_V4, *LPRILMANAGECALLSPARAMS_V4, RILMANAGECALLSPARAMS, RILMANAGECALLSPARAMS_V4
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
req.alt-api: RILMANAGECALLSPARAMS_V4
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

# RILMANAGECALLSPARAMS_V4 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILMANAGECALLSPARAMS_V4 {
  DWORD                       dwExecutor;
  RILMANAGECALLPARAMSCOMMAND  dwCommand;
  DWORD                       dwID;
  BOOL                        fHasOfferAnswer;
  RILCALLMEDIAOFFERANSWERSET  rcmOfferAnswer;
  RILADDRESS                  raAddress;
  RILCALLRTTACTION            dwRTTAction;
} RILMANAGECALLSPARAMS_V4, RILMANAGECALLSPARAMS_V4;
````


## -struct-fields

### -field dwExecutor


### -field dwCommand


### -field dwID


### -field fHasOfferAnswer


### -field rcmOfferAnswer


### -field raAddress


### -field dwRTTAction


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