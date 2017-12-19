---
UID: NS.KS.KSPIN_MDL_CACHING_NOTIFICATION32
title: KSPIN_MDL_CACHING_NOTIFICATION32
author: windows-driver-content
description: This structure is used internally by the operating system.
old-location: stream\kspin_mdl_caching_notification32.htm
old-project: stream
ms.assetid: 36C07734-20FC-4330-8BB1-535E8581162D
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KSPIN_MDL_CACHING_NOTIFICATION32, *PKSPIN_MDL_CACHING_NOTIFICATION32, PKSPIN_MDL_CACHING_NOTIFICATION32, KSPIN_MDL_CACHING_NOTIFICATION32
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSPIN_MDL_CACHING_NOTIFICATION32
req.alt-loc: ks.h
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

# KSPIN_MDL_CACHING_NOTIFICATION32 structure



## -description
This structure is used internally by the operating system.



## -syntax

````
typedef struct {
  KSPIN_MDL_CACHING_EVENT Event;
  ULONG                   Buffer;
} KSPIN_MDL_CACHING_NOTIFICATION32, *PKSPIN_MDL_CACHING_NOTIFICATION32;
````


## -struct-fields

### -field Event

This member is used internally by the operating system.


### -field Buffer

This member  is used internally by the operating system.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>