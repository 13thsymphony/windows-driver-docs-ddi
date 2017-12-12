---
UID: NS.NTDDRILAPITYPES.RILRADIOCONFIGURATIONS
title: RILRADIOCONFIGURATIONS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradioconfigurations.htm
old-project: netvista
ms.assetid: 28908305-69aa-4bf0-98a1-6cee4aa1c349
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILRADIOCONFIGURATIONS, RILRADIOCONFIGURATIONS, *LPRILRADIOCONFIGURATIONS
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
req.alt-api: RILRADIOCONFIGURATIONS
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

# RILRADIOCONFIGURATIONS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILRADIOCONFIGURATIONS {
  DWORD                     dwNumberOfConfigurations;
  RILRADIOCONFIGURATION [1] stConfigurations;
} RILRADIOCONFIGURATIONS, RILRADIOCONFIGURATIONS;
````


## -struct-fields

### -field dwNumberOfConfigurations


### -field stConfigurations


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