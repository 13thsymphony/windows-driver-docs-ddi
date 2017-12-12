---
UID: NS.RILAPITYPES.RILTERMINALCAPABILITYINFO~R1
title: RILTERMINALCAPABILITYINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilterminalcapabilityinfo_2.htm
old-project: netvista
ms.assetid: 29d9bf92-ea35-4d74-bc4c-3f386e7fb3fa
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILTERMINALCAPABILITYINFO, RILTERMINALCAPABILITYINFO, *LPRILTERMINALCAPABILITYINFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILTERMINALCAPABILITYINFO
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

# RILTERMINALCAPABILITYINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILTERMINALCAPABILITYINFO {
  DWORD                            dwSize;
  BYTE [MAXTERMINALCAPABILITYSIZE] bData;
} RILTERMINALCAPABILITYINFO, RILTERMINALCAPABILITYINFO;
````


## -struct-fields

### -field dwSize


### -field bData


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