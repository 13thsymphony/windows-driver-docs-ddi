---
UID: NS.RILAPITYPES.RILPSMEDIACONFIGURATIONSET
title: RILPSMEDIACONFIGURATIONSET
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpsmediaconfigurationset_2.htm
old-project: NetVista
ms.assetid: cdaa161e-2481-497c-8a9b-4c07a3d99d1f
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILPSMEDIACONFIGURATIONSET, *LPRILPSMEDIACONFIGURATIONSET, RILPSMEDIACONFIGURATIONSET
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
req.alt-api: RILPSMEDIACONFIGURATIONSET
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

# RILPSMEDIACONFIGURATIONSET structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILPSMEDIACONFIGURATIONSET {
  DWORD                       cbSize;
  DWORD                       dwExecutor;
  DWORD                       dwNumMediaConfiguration;
  RILPSMEDIACONFIGURATION [1] stMediaConfiguration;
} RILPSMEDIACONFIGURATIONSET, RILPSMEDIACONFIGURATIONSET;
````


## -struct-fields

### -field cbSize


### -field dwExecutor


### -field dwNumMediaConfiguration


### -field stMediaConfiguration


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