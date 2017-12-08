---
UID: NS.RILAPITYPES.RILDISPLAYINFO
title: RILDISPLAYINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rildisplayinfo_2.htm
old-project: netvista
ms.assetid: f24d8122-ea07-477f-9cf9-4767cc0fbf86
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: RILDISPLAYINFO, *LPRILDISPLAYINFO, RILDISPLAYINFO
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
req.alt-api: RILDISPLAYINFO
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

# RILDISPLAYINFO structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax

````
typedef struct _RILDISPLAYINFO {
  DWORD               cbSize;
  DWORD               dwParams;
  DWORD               dwExecutor;
  RILDISPLAYINFOTYPE  dwType;
  RILDISPLAYINFOTAG   dwTag;
  DWORD               dwMessageSize;
  BYTE [1]            pbMessage;
} RILDISPLAYINFO, RILDISPLAYINFO;
````


## -struct-fields

### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwType


### -field dwTag


### -field dwMessageSize


### -field pbMessage


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