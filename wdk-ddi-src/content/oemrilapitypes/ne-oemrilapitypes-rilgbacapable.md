---
UID: NE:oemrilapitypes.RILGBACAPABLE
title: RILGBACAPABLE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgbacapable.htm
old-project: netvista
ms.assetid: c1acc574-6e9e-40a1-8892-00572fcc545c
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILGBACAPABLE, RILGBACAPABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: oemrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILGBACAPABLE
req.alt-loc: oemrilapitypes.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: RILGBACAPABLE
---

# RILGBACAPABLE enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILGBACAPABLE { 
  RIL_GBA_UNKNOWN,
  RIL_GBA_NOT_SUPPORTED,
  RIL_GBA_ME_SUPPORTED,
  RIL_GBA_U_SUPPORTED
} RILGBACAPABLE;
````


## -enum-fields

### -field RIL_GBA_UNKNOWN


### -field RIL_GBA_NOT_SUPPORTED


### -field RIL_GBA_ME_SUPPORTED


### -field RIL_GBA_U_SUPPORTED


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Oemrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>