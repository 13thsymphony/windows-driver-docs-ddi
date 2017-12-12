---
UID: NE.ntddrilapitypes.RILMSGMWISUMMARYLISTPARAMMASK
title: RILMSGMWISUMMARYLISTPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwisummarylistparammask.htm
old-project: netvista
ms.assetid: f7b9d558-7c95-40d5-9740-ae1b9f7595c1
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILMSGMWISUMMARYLISTPARAMMASK, RILMSGMWISUMMARYLISTPARAMMASK
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
req.alt-api: RILMSGMWISUMMARYLISTPARAMMASK
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

# RILMSGMWISUMMARYLISTPARAMMASK enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.



## -syntax

````
typedef enum _RILMSGMWISUMMARYLISTPARAMMASK { 
  RIL_PARAM_MWISUMMARY_REFNUM,
  RIL_PARAM_MWISUMMARY_ACCTADDR,
  RIL_PARAM_MWISUMMARY_TOTALNUMDETAILITEMS,
  RIL_PARAM_MWISUMMARY_NUMSUMMARYITEMS,
  RIL_PARAM_MWISUMMARY_SUMMARYITEMS,
  RIL_PARAM_MWISUMMARY_ALL
} RILMSGMWISUMMARYLISTPARAMMASK;
````


## -enum-fields

### -field RIL_PARAM_MWISUMMARY_REFNUM


### -field RIL_PARAM_MWISUMMARY_ACCTADDR


### -field RIL_PARAM_MWISUMMARY_TOTALNUMDETAILITEMS


### -field RIL_PARAM_MWISUMMARY_NUMSUMMARYITEMS


### -field RIL_PARAM_MWISUMMARY_SUMMARYITEMS


### -field RIL_PARAM_MWISUMMARY_ALL


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