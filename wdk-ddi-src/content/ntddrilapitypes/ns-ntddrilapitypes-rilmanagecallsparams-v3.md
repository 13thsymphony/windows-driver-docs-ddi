---
UID: NS.ntddrilapitypes.RILMANAGECALLSPARAMS_V3
title: RILMANAGECALLSPARAMS_V3
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmanagecallsparams_v3.htm
old-project: netvista
ms.assetid: a398086b-827e-4684-a79c-db849926b3c3
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILMANAGECALLSPARAMS_V3, RILMANAGECALLSPARAMS_V3, *LPRILMANAGECALLSPARAMS_V3
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
req.alt-api: RILMANAGECALLSPARAMS_V3
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

# RILMANAGECALLSPARAMS_V3 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILMANAGECALLSPARAMS_V3 {
  DWORD                       dwExecutor;
  RILMANAGECALLPARAMSCOMMAND  dwCommand;
  DWORD                       dwID;
  BOOL                        fHasOfferAnswer;
  RILCALLMEDIAOFFERANSWERSET  rcmOfferAnswer;
  RILADDRESS                  raAddress;
} RILMANAGECALLSPARAMS_V3, RILMANAGECALLSPARAMS_V3;
````


## -struct-fields
<dl>

### -field dwExecutor

<dd></dd>

### -field dwCommand

<dd></dd>

### -field dwID

<dd></dd>

### -field fHasOfferAnswer

<dd></dd>

### -field rcmOfferAnswer

<dd></dd>

### -field raAddress

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