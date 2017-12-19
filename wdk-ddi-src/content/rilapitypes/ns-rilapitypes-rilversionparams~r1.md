---
UID: NS.RILAPITYPES.RILVERSIONPARAMS~R1
title: RILVERSIONPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilversionparams_2.htm
old-project: NetVista
ms.assetid: 365230b4-fd09-413f-9174-a5c5576a9160
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILVERSIONPARAMS, RILVERSIONPARAMS, *LPRILVERSIONPARAMS
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
req.alt-api: RILVERSIONPARAMS
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

# RILVERSIONPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILVERSIONPARAMS {
  WORD  Minor;
  WORD  Major;
} RILVERSIONPARAMS, RILVERSIONPARAMS;
````


## -struct-fields

### -field Minor


### -field Major


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