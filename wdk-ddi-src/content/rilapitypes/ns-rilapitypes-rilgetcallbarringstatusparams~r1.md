---
UID: NS.RILAPITYPES.RILGETCALLBARRINGSTATUSPARAMS~R1
title: RILGETCALLBARRINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetcallbarringstatusparams_2.htm
old-project: netvista
ms.assetid: 1a33d682-5413-4026-8e43-e83548f688c5
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILGETCALLBARRINGSTATUSPARAMS, *LPRILGETCALLBARRINGSTATUSPARAMS, RILGETCALLBARRINGSTATUSPARAMS
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
req.alt-api: RILGETCALLBARRINGSTATUSPARAMS
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

# RILGETCALLBARRINGSTATUSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILGETCALLBARRINGSTATUSPARAMS {
  DWORD                           dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE  dwType;
  BOOL                            fAllClasses;
  DWORD                           dwInfoClasses;
} RILGETCALLBARRINGSTATUSPARAMS, RILGETCALLBARRINGSTATUSPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwType


### -field fAllClasses


### -field dwInfoClasses


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