---
UID: NE.rilapitypes.RILRFSTATEPARAMMASK
title: RILRFSTATEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrfstateparammask_2.htm
old-project: netvista
ms.assetid: 075c61aa-b091-4616-810b-f39ad40d2777
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILRFSTATEPARAMMASK, RILRFSTATEPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILRFSTATEPARAMMASK
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

# RILRFSTATEPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef enum _RILRFSTATEPARAMMASK { 
  RIL_PARAM_RFSTATE_RFSTATE,
  RIL_PARAM_RFSTATE_RFDATASIZE,
  RIL_PARAM_RFSTATE_RFDATA,
  RIL_PARAM_RFSTATE_ALL
} RILRFSTATEPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_RFSTATE_RFSTATE


### -field RIL_PARAM_RFSTATE_RFDATASIZE


### -field RIL_PARAM_RFSTATE_RFDATA


### -field RIL_PARAM_RFSTATE_ALL


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