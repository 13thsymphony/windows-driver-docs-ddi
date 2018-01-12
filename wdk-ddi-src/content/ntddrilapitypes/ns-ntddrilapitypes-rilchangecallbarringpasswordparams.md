---
UID: NS:ntddrilapitypes.RILCHANGECALLBARRINGPASSWORDPARAMS
title: RILCHANGECALLBARRINGPASSWORDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilchangecallbarringpasswordparams.htm
old-project: netvista
ms.assetid: 9b90f85e-091f-465d-a6e2-fa4ad66489ff
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILCHANGECALLBARRINGPASSWORDPARAMS, *LPRILCHANGECALLBARRINGPASSWORDPARAMS, RILCHANGECALLBARRINGPASSWORDPARAMS
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
req.alt-api: RILCHANGECALLBARRINGPASSWORDPARAMS
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
req.typenames: *LPRILCHANGECALLBARRINGPASSWORDPARAMS, RILCHANGECALLBARRINGPASSWORDPARAMS
---

# RILCHANGECALLBARRINGPASSWORDPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILCHANGECALLBARRINGPASSWORDPARAMS {
  DWORD                           dwExecutor;
  RILCALLBARRINGSTATUSPARAMSTYPE  dwType;
  char [256]                      szOldPassword;
  char [256]                      szNewPassword;
  char [256]                      szConfirmPassword;
} RILCHANGECALLBARRINGPASSWORDPARAMS, RILCHANGECALLBARRINGPASSWORDPARAMS;
````


## -struct-fields

### -field dwExecutor


### -field dwType


### -field szOldPassword


### -field szNewPassword


### -field szConfirmPassword


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