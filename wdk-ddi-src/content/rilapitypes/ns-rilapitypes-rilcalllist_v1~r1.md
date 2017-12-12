---
UID: NS.RILAPITYPES.RILCALLLIST_V1~R1
title: RILCALLLIST_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalllist_v1_2.htm
old-project: netvista
ms.assetid: bdca275c-c728-4be4-bb57-cfa61cddff61
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: RILCALLLIST_V1, RILCALLLIST_V1, *LPRILCALLLIST_V1
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
req.alt-api: RILCALLLIST_V1
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

# RILCALLLIST_V1 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCALLLIST_V1 {
  DWORD              dwNumberOfCalls;
  RILCALLINFO_V1 [1] rciCallInfo;
} RILCALLLIST_V1, RILCALLLIST_V1;
````


## -struct-fields

### -field dwNumberOfCalls


### -field rciCallInfo


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