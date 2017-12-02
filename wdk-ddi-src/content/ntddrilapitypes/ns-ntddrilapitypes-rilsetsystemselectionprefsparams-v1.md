---
UID: NS.ntddrilapitypes.RILSETSYSTEMSELECTIONPREFSPARAMS_V1
title: RILSETSYSTEMSELECTIONPREFSPARAMS_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsetsystemselectionprefsparams_v1.htm
old-project: netvista
ms.assetid: 9b5cbd12-76b1-492e-828e-39a955f6d15c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RILSETSYSTEMSELECTIONPREFSPARAMS_V1, RILSETSYSTEMSELECTIONPREFSPARAMS_V1, *LPRILSETSYSTEMSELECTIONPREFSPARAMS_V1
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
req.alt-api: RILSETSYSTEMSELECTIONPREFSPARAMS_V1
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

# RILSETSYSTEMSELECTIONPREFSPARAMS_V1 structure



## -description
<p>This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.</p>


## -syntax

````
typedef struct _RILSETSYSTEMSELECTIONPREFSPARAMS_V1 {
  DWORD                       dwFlags;
  RILSYSTEMSELECTIONPREFS_V1  rilSystemSelectionPrefs;
} RILSETSYSTEMSELECTIONPREFSPARAMS_V1, RILSETSYSTEMSELECTIONPREFSPARAMS_V1;
````


## -struct-fields
<dl>

### -field dwFlags

<dd></dd>

### -field rilSystemSelectionPrefs

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