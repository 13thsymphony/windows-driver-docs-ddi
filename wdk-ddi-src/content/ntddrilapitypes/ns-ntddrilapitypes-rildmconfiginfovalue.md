---
UID: NS.NTDDRILAPITYPES.RILDMCONFIGINFOVALUE
title: RILDMCONFIGINFOVALUE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildmconfiginfovalue.htm
old-project: netvista
ms.assetid: dda43544-4609-4674-9616-8e09939f0c39
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILDMCONFIGINFOVALUE, *LPRILDMCONFIGINFOVALUE, RILDMCONFIGINFOVALUE
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
req.alt-api: RILDMCONFIGINFOVALUE
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

# RILDMCONFIGINFOVALUE structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILDMCONFIGINFOVALUE {
  DWORD                cbSize;
  RILDMCONFIGINFOTYPE  dwType;
  BOOL                 fValue;
  DWORD                dwValue;
  WCHAR [256]          wszValue;
} RILDMCONFIGINFOVALUE, RILDMCONFIGINFOVALUE;
````


## -struct-fields

### -field cbSize


### -field dwType


### -field fValue


### -field dwValue


### -field wszValue


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