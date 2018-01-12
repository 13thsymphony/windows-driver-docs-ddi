---
UID: NE:ntddrilapitypes.RILSIGNALQUALITYPARAMMASK
title: RILSIGNALQUALITYPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsignalqualityparammask.htm
old-project: netvista
ms.assetid: cf6727dc-e6f3-418e-bee4-e372dcc29a66
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILSIGNALQUALITYPARAMMASK, RILSIGNALQUALITYPARAMMASK
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
req.alt-api: RILSIGNALQUALITYPARAMMASK
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
req.typenames: RILSIGNALQUALITYPARAMMASK
---

# RILSIGNALQUALITYPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILSIGNALQUALITYPARAMMASK { 
  RIL_PARAM_SQ_SYSTEMTYPE,
  RIL_PARAM_SQ_NUMSIGNALBARS,
  RIL_PARAM_SQ_SIGNALSTRENGTH,
  RIL_PARAM_SQ_SNR,
  RIL_PARAM_SQ_ALL
} RILSIGNALQUALITYPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_SQ_SYSTEMTYPE


### -field RIL_PARAM_SQ_NUMSIGNALBARS


### -field RIL_PARAM_SQ_SIGNALSTRENGTH


### -field RIL_PARAM_SQ_SNR


### -field RIL_PARAM_SQ_ALL


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