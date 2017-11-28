---
UID: NS.ntddrilapitypes.RILCHANGEUICCLOCKPASSWORDPARAMS
title: RILCHANGEUICCLOCKPASSWORDPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilchangeuicclockpasswordparams.htm
old-project: netvista
ms.assetid: 00e2fe6f-fd8b-45d1-9fd2-d90c515c3571
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: RILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS, *LPRILCHANGEUICCLOCKPASSWORDPARAMS
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
req.alt-api: RILCHANGEUICCLOCKPASSWORDPARAMS
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

# RILCHANGEUICCLOCKPASSWORDPARAMS structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILCHANGEUICCLOCKPASSWORDPARAMS {
  RILUICCLOCKCREDENTIAL  lockCredential;
  char [256]             szNewPassword;
} RILCHANGEUICCLOCKPASSWORDPARAMS, RILCHANGEUICCLOCKPASSWORDPARAMS;
````


## -struct-fields
<dl>

### -field <b>lockCredential</b>

<dd></dd>

### -field <b>szNewPassword</b>

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