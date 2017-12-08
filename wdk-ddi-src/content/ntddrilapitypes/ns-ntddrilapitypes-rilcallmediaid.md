---
UID: NS.NTDDRILAPITYPES.RILCALLMEDIAID
title: RILCALLMEDIAID
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaid.htm
old-project: netvista
ms.assetid: de55805d-d5fe-47ea-832d-536d8a7ee257
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILCALLMEDIAID, *LPRILCALLMEDIAID, RILCALLMEDIAID
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
req.alt-api: RILCALLMEDIAID
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

# RILCALLMEDIAID structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILCALLMEDIAID {
  RILCALLMEDIATYPE  dwType;
  DWORD             dwID;
} RILCALLMEDIAID, RILCALLMEDIAID;
````


## -struct-fields

### -field dwType


### -field dwID


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