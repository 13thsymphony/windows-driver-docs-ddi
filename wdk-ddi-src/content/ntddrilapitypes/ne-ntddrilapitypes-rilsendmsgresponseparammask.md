---
UID: NE:ntddrilapitypes.RILSENDMSGRESPONSEPARAMMASK
title: RILSENDMSGRESPONSEPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsendmsgresponseparammask.htm
old-project: netvista
ms.assetid: d3bf2b1a-22ac-4b37-a442-ecd8a2108b46
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILSENDMSGRESPONSEPARAMMASK, RILSENDMSGRESPONSEPARAMMASK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILSENDMSGRESPONSEPARAMMASK
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
req.typenames: RILSENDMSGRESPONSEPARAMMASK
---

# RILSENDMSGRESPONSEPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILSENDMSGRESPONSEPARAMMASK { 
  RIL_PARAM_MSGRES_CDMACAUSECODE,
  RIL_PARAM_MSGRES_CDMAERRORCLASS,
  RIL_PARAM_MSGRES_GWLTRANSPORTCODE,
  RIL_PARAM_MSGRES_GWLRELAYCODE,
  RIL_PARAM_MSGRES_MSGID,
  RIL_PARAM_MSGRES_ALL
} RILSENDMSGRESPONSEPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_MSGRES_CDMACAUSECODE


### -field RIL_PARAM_MSGRES_CDMAERRORCLASS


### -field RIL_PARAM_MSGRES_GWLTRANSPORTCODE


### -field RIL_PARAM_MSGRES_GWLRELAYCODE


### -field RIL_PARAM_MSGRES_MSGID


### -field RIL_PARAM_MSGRES_ALL


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