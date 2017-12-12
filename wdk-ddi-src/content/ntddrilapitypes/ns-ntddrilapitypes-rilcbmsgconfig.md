---
UID: NS.NTDDRILAPITYPES.RILCBMSGCONFIG
title: RILCBMSGCONFIG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcbmsgconfig.htm
old-project: netvista
ms.assetid: c59f26b7-47ce-4bf9-b678-a2bb48c69754
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILCBMSGCONFIG, RILCBMSGCONFIG, *LPRILCBMSGCONFIG
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
req.alt-api: RILCBMSGCONFIG
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

# RILCBMSGCONFIG structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILCBMSGCONFIG {
  DWORD                    cbSize;
  DWORD                    dwParams;
  DWORD                    dwGWLConfigInfoSize;
  RILCBGWLCONFIGINFO [50]  GWLConfigInfo;
  DWORD                    dwCDMAConfigInfoSize;
  RILCBCDMACONFIGINFO [50] CDMAConfigInfo;
} RILCBMSGCONFIG, RILCBMSGCONFIG;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwGWLConfigInfoSize


### -field GWLConfigInfo


### -field dwCDMAConfigInfoSize


### -field CDMAConfigInfo


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