---
UID: NS.NTDDRILAPITYPES.RILCALLHANDOVERSTATE
title: RILCALLHANDOVERSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallhandoverstate.htm
old-project: netvista
ms.assetid: 1c9fb343-32f1-444e-9328-097da72cd006
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILCALLHANDOVERSTATE, *LPRILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE
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
req.alt-api: RILCALLHANDOVERSTATE
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

# RILCALLHANDOVERSTATE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILCALLHANDOVERSTATE {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RILCALLHANDOVERPHASE  dwPhase;
  RILCALLTYPE           dwOldType;
  RILCALLTYPE           dwNewType;
  DWORD                 dw3gppCause;
} RILCALLHANDOVERSTATE, RILCALLHANDOVERSTATE;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwPhase


### -field dwOldType


### -field dwNewType


### -field dw3gppCause


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