---
UID: NE.wditypes._WDI_IHV_TASK_PRIORITY
title: _WDI_IHV_TASK_PRIORITY
author: windows-driver-content
description: The WDI_IHV_TASK_PRIORITY enumeration defines IHV task priorities.
old-location: netvista\wdi_ihv_task_priority.htm
old-project: netvista
ms.assetid: 606CF45C-5398-4157-92A7-382B6162D806
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WDI_IHV_TASK_PRIORITY, WDI_IHV_TASK_PRIORITY
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wditypes.hpp
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_IHV_TASK_PRIORITY
req.alt-loc: wditypes.hpp
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

# _WDI_IHV_TASK_PRIORITY enumeration



## -description
The WDI_IHV_TASK_PRIORITY enumeration defines IHV task priorities.


## -syntax

````
typedef enum _WDI_IHV_TASK_PRIORITY { 
  WDI_IHV_TASK_PRIORITY_HIGH    = 1,
  WDI_IHV_TASK_PRIORITY_MEDIUM  = 2,
  WDI_IHV_TASK_PRIORITY_LOW     = 3
} WDI_IHV_TASK_PRIORITY;
````


## -enum-fields

### -field WDI_IHV_TASK_PRIORITY_HIGH

High priority.

### -field WDI_IHV_TASK_PRIORITY_MEDIUM

Medium priority.

### -field WDI_IHV_TASK_PRIORITY_LOW

Low priority.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wditypes.hpp</dt>
</dl>
</td>
</tr>
</table>