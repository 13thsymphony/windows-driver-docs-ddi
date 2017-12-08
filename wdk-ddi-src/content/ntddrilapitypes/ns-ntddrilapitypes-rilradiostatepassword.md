---
UID: NS.NTDDRILAPITYPES.RILRADIOSTATEPASSWORD
title: RILRADIOSTATEPASSWORD
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilradiostatepassword.htm
old-project: netvista
ms.assetid: 5329a688-ca72-456c-b9fa-32a922783d97
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD, *LPRILRADIOSTATEPASSWORD
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
req.alt-api: RILRADIOSTATEPASSWORD
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

# RILRADIOSTATEPASSWORD structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef struct _RILRADIOSTATEPASSWORD {
  DWORD      dwPasswordId;
  WCHAR [32] wszPassword;
} RILRADIOSTATEPASSWORD, RILRADIOSTATEPASSWORD;
````


## -struct-fields

### -field dwPasswordId


### -field wszPassword


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