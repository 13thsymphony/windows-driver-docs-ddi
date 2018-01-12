---
UID: NS:ntddrilapitypes.RILDEACTIVATEPERSOPARAMS
title: RILDEACTIVATEPERSOPARAMS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildeactivatepersoparams.htm
old-project: netvista
ms.assetid: 408ae5d4-f83f-4e4a-9850-a7bae70a2da2
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILDEACTIVATEPERSOPARAMS, *LPRILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS
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
req.alt-api: RILDEACTIVATEPERSOPARAMS
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
req.typenames: *LPRILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS
---

# RILDEACTIVATEPERSOPARAMS structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef struct _RILDEACTIVATEPERSOPARAMS {
  DWORD      dwPersoFeature;
  char [256] szPassword;
} RILDEACTIVATEPERSOPARAMS, RILDEACTIVATEPERSOPARAMS;
````


## -struct-fields

### -field dwPersoFeature


### -field szPassword


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