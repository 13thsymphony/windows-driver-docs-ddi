---
UID: NE.rilapitypes.RILIMSSSTATUSPARAMMASK
title: RILIMSSSTATUSPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilimssstatusparammask_2.htm
old-project: netvista
ms.assetid: 0d5896e8-b85e-407c-8b3e-cc8ad95c2ab1
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILIMSSSTATUSPARAMMASK, RILIMSSSTATUSPARAMMASK
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
req.alt-api: RILIMSSSTATUSPARAMMASK
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

# RILIMSSSTATUSPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILIMSSSTATUSPARAMMASK { 
  RIL_PARAM_IMSSTATUS_HUICCAPP,
  RIL_PARAM_IMSSTATUS_AVAILABLESERVICES,
  RIL_PARAM_IMSSTATUS_SMSSUPPORTEDFORMAT,
  RIL_PARAM_IMSSTATUS_SERVINGDOMAIN,
  RIL_PARAM_IMSSTATUS_SYSTEMTYPE,
  RIL_PARAM_IMSSTATUS_ALL
} RILIMSSSTATUSPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_IMSSTATUS_HUICCAPP


### -field RIL_PARAM_IMSSTATUS_AVAILABLESERVICES


### -field RIL_PARAM_IMSSTATUS_SMSSUPPORTEDFORMAT


### -field RIL_PARAM_IMSSTATUS_SERVINGDOMAIN


### -field RIL_PARAM_IMSSTATUS_SYSTEMTYPE


### -field RIL_PARAM_IMSSTATUS_ALL


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