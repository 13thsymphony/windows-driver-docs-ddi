---
UID: NS:rilapitypes.RILSETCALLBARRINGSTATUSPARAMS
title: RILSETCALLBARRINGSTATUSPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetcallbarringstatusparams_2.htm
old-project: netvista
ms.assetid: 6116e564-93e6-45ba-8759-aab7d82783b2
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILSETCALLBARRINGSTATUSPARAMS, *LPRILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS
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
req.alt-api: RILSETCALLBARRINGSTATUSPARAMS
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
req.typenames: *LPRILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS
req.product: Windows 10 or later.
---

# RILSETCALLBARRINGSTATUSPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILSETCALLBARRINGSTATUSPARAMS {
  DWORD                             dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE    dwType;
  BOOL                              fAllClasses;
  DWORD                             dwInfoClasses;
  BOOL                              fPassword;
  char [MAXLENGTH_PASSWORD]         szPassword;
  RILCALLBARRINGSTATUSPARAMSSTATUS  dwStatus;
} RILSETCALLBARRINGSTATUSPARAMS, RILSETCALLBARRINGSTATUSPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwType


### -field fAllClasses


### -field dwInfoClasses


### -field fPassword


### -field szPassword


### -field dwStatus


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