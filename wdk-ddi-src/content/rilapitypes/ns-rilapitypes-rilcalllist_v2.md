---
UID: NS:rilapitypes.RILCALLLIST_V2
title: RILCALLLIST_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalllist_v2_2.htm
old-project: netvista
ms.assetid: ecc08fed-deee-4b94-84ae-05159447abf3
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILCALLLIST_V2, *LPRILCALLLIST_V2, RILCALLLIST_V2
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
req.alt-api: RILCALLLIST_V2
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
req.typenames: *LPRILCALLLIST_V2, RILCALLLIST_V2
req.product: Windows 10 or later.
---

# RILCALLLIST_V2 structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILCALLLIST_V2 {
  DWORD              dwNumberOfCalls;
  RILCALLINFO_V2 [1] rciCallInfo;
} RILCALLLIST_V2, RILCALLLIST_V2;
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