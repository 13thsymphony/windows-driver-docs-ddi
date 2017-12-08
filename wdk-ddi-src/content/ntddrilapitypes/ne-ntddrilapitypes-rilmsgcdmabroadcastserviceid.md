---
UID: NE.ntddrilapitypes.RILMSGCDMABROADCASTSERVICEID
title: RILMSGCDMABROADCASTSERVICEID
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmabroadcastserviceid.htm
old-project: netvista
ms.assetid: 71f887ed-ab80-4b5f-bc74-d4333984fdd2
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILMSGCDMABROADCASTSERVICEID, RILMSGCDMABROADCASTSERVICEID
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
req.alt-api: RILMSGCDMABROADCASTSERVICEID
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

# RILMSGCDMABROADCASTSERVICEID enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax

````
typedef enum _RILMSGCDMABROADCASTSERVICEID { 
  RIL_1xBROADCAST_CMAS_EXTREME,
  RIL_1xBROADCAST_CMAS_SEVERE,
  RIL_1xBROADCAST_CMAS_AMBER,
  RIL_1xBROADCAST_CMAS_TEST
} RILMSGCDMABROADCASTSERVICEID;
````


## -enum-fields

### -field RIL_1xBROADCAST_CMAS_EXTREME


### -field RIL_1xBROADCAST_CMAS_SEVERE


### -field RIL_1xBROADCAST_CMAS_AMBER


### -field RIL_1xBROADCAST_CMAS_TEST


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