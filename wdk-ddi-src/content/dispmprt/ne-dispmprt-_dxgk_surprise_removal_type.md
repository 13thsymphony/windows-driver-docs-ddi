---
UID: NE.dispmprt._DXGK_SURPRISE_REMOVAL_TYPE
title: _DXGK_SURPRISE_REMOVAL_TYPE
author: windows-driver-content
description: Indicates the type of surprise removal event when an external display device is disconnected from the system.
old-location: display\dxgk_surprise_removal_type.htm
old-project: display
ms.assetid: 3045f46d-d78a-4f07-9838-f3afd97d9244
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_SURPRISE_REMOVAL_TYPE, DXGK_SURPRISE_REMOVAL_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_SURPRISE_REMOVAL_TYPE
req.alt-loc: Dispmprt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
---

# _DXGK_SURPRISE_REMOVAL_TYPE enumeration



## -description
Indicates the type of surprise removal event when an external display device is disconnected  from the system.



## -syntax

````
typedef enum _DXGK_SURPRISE_REMOVAL_TYPE { 
  DxgkRemovalHibernation  = 0
} DXGK_SURPRISE_REMOVAL_TYPE;
````


## -enum-fields

### -field DxgkRemovalHibernation

The disconnected external display device was in hibernation mode.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h)</dt>
</dl>
</td>
</tr>
</table>