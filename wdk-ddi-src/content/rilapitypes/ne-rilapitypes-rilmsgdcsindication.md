---
UID: NE.rilapitypes.RILMSGDCSINDICATION
title: RILMSGDCSINDICATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsindication_2.htm
old-project: netvista
ms.assetid: 292f54d6-0555-47d0-97b9-b76e9e08bf78
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILMSGDCSINDICATION, RILMSGDCSINDICATION
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
req.alt-api: RILMSGDCSINDICATION
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

# RILMSGDCSINDICATION enumeration



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef enum _RILMSGDCSINDICATION { 
  RIL_DCSINDICATION_FAX,
  RIL_DCSINDICATION_EMAIL,
  RIL_DCSINDICATION_OTHER,
  RIL_DCSINDICATION_MAX
} RILMSGDCSINDICATION;
````


## -enum-fields

### -field RIL_DCSINDICATION_FAX


### -field RIL_DCSINDICATION_EMAIL


### -field RIL_DCSINDICATION_OTHER


### -field RIL_DCSINDICATION_MAX


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