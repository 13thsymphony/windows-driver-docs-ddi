---
UID: NE.rilapitypes.RILLTEKIND
title: RILLTEKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilltekind_2.htm
old-project: netvista
ms.assetid: ab80e0a2-d404-4333-8a3e-f8e74d8c7f20
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILLTEKIND, RILLTEKIND
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
req.alt-api: RILLTEKIND
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

# RILLTEKIND enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILLTEKIND { 
  RIL_LTEKIND_FDD,
  RIL_LTEKIND_TDD,
  RIL_LTEKIND_RESERVED,
  RIL_LTEKIND_UNKNOWN_CA,
  RIL_LTEKIND_FDD_CA,
  RIL_LTEKIND_TDD_CA,
  RIL_LTEKIND_MAX
} RILLTEKIND;
````


## -enum-fields

### -field RIL_LTEKIND_FDD


### -field RIL_LTEKIND_TDD


### -field RIL_LTEKIND_RESERVED


### -field RIL_LTEKIND_UNKNOWN_CA


### -field RIL_LTEKIND_FDD_CA


### -field RIL_LTEKIND_TDD_CA


### -field RIL_LTEKIND_MAX


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