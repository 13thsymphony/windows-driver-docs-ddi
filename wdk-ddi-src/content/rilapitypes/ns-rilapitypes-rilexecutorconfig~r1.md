---
UID: NS.RILAPITYPES.RILEXECUTORCONFIG~R1
title: RILEXECUTORCONFIG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorconfig_2.htm
old-project: NetVista
ms.assetid: 8f10bb0f-2a9e-4310-946d-c1c9250391e7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RILEXECUTORCONFIG, *LPRILEXECUTORCONFIG, RILEXECUTORCONFIG
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
req.alt-api: RILEXECUTORCONFIG
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

# RILEXECUTORCONFIG structure



## -description
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 



## -syntax

````
typedef struct _RILEXECUTORCONFIG {
  DWORD                           cbSize;
  DWORD                           dwFlags;
  DWORD                           dwNumApps;
  HUICCAPP [MAXNUM_EXECUTOR_APPS] lphUiccApps;
} RILEXECUTORCONFIG, RILEXECUTORCONFIG;
````


## -struct-fields

### -field cbSize


### -field dwFlags


### -field dwNumApps


### -field lphUiccApps


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