---
UID: NS.NTDDRILAPITYPES.RILRADIOSTATEGROUPS
title: RILRADIOSTATEGROUPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostategroups.htm
old-project: netvista
ms.assetid: 901fe9e5-4b3c-4f31-9bf0-a4a5bd66bd19
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILRADIOSTATEGROUPS, RILRADIOSTATEGROUPS, *LPRILRADIOSTATEGROUPS
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
req.alt-api: RILRADIOSTATEGROUPS
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

# RILRADIOSTATEGROUPS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILRADIOSTATEGROUPS {
  DWORD                  dwCntGroups;
  RILRADIOSTATEGROUP [1] rilGroups;
} RILRADIOSTATEGROUPS, RILRADIOSTATEGROUPS;
````


## -struct-fields

### -field dwCntGroups


### -field rilGroups


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