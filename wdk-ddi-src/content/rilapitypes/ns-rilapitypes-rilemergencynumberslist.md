---
UID: NS.RILAPITYPES.RILEMERGENCYNUMBERSLIST
title: RILEMERGENCYNUMBERSLIST
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumberslist_2.htm
old-project: netvista
ms.assetid: 06816431-a6fc-4c24-a31d-c486a4ba667f
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILEMERGENCYNUMBERSLIST, *LPRILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST
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
req.alt-api: RILEMERGENCYNUMBERSLIST
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

# RILEMERGENCYNUMBERSLIST structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILEMERGENCYNUMBERSLIST {
  DWORD                  cbSize;
  DWORD                  dwRilENSize;
  RILEMERGENCYNUMBER [1] RilEN;
} RILEMERGENCYNUMBERSLIST, RILEMERGENCYNUMBERSLIST;
````


## -struct-fields

### -field cbSize


### -field dwRilENSize


### -field RilEN


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