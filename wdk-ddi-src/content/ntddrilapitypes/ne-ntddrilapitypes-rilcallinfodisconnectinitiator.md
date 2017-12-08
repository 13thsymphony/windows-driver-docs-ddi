---
UID: NE.ntddrilapitypes.RILCALLINFODISCONNECTINITIATOR
title: RILCALLINFODISCONNECTINITIATOR
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfodisconnectinitiator.htm
old-project: netvista
ms.assetid: df3c3cb9-583c-4a6e-9477-843067865418
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILCALLINFODISCONNECTINITIATOR, RILCALLINFODISCONNECTINITIATOR
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCALLINFODISCONNECTINITIATOR
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

# RILCALLINFODISCONNECTINITIATOR enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef enum _RILCALLINFODISCONNECTINITIATOR { 
  RIL_DISCINIT_LOCAL,
  RIL_DISCINIT_REMOTE,
  RIL_DISCINIT_MAX
} RILCALLINFODISCONNECTINITIATOR;
````


## -enum-fields

### -field RIL_DISCINIT_LOCAL


### -field RIL_DISCINIT_REMOTE


### -field RIL_DISCINIT_MAX


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