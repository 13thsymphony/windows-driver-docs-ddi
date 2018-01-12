---
UID: NS:ntddrilapitypes.RILCALLLIST_V2
title: RILCALLLIST_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcalllist_v2.htm
old-project: netvista
ms.assetid: 4cf94a04-dbb4-4e24-954b-3a5a720ef963
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: RILCALLLIST_V2, *LPRILCALLLIST_V2, RILCALLLIST_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILCALLLIST_V2
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
req.typenames: *LPRILCALLLIST_V2, RILCALLLIST_V2
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
<dt>Ntddrilapitypes.h</dt>
</dl>
</td>
</tr>
</table>