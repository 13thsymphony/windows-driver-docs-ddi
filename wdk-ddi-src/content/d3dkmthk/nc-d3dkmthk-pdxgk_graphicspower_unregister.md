---
UID: NC.d3dkmthk.PDXGK_GRAPHICSPOWER_UNREGISTER
title: PDXGK_GRAPHICSPOWER_UNREGISTER
author: windows-driver-content
description: A callback to un-register itself with the graphics driver.
old-location: display\pdxgk_graphicspower_unregister.htm
old-project: display
ms.assetid: A925D5D3-EF79-4C14-BE1C-188C255DDF8E
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_TARGETMODE_DETAIL_TIMING, DXGK_TARGETMODE_DETAIL_TIMING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmthk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PDXGK_GRAPHICSPOWER_UNREGISTER
req.alt-loc: d3dkmthk.h
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

# PDXGK_GRAPHICSPOWER_UNREGISTER callback



## -description
A callback to un-register itself with the graphics driver.  



## -prototype

````
NTSTATUS PDXGK_GRAPHICSPOWER_UNREGISTER(
   PVOID DeviceHandle,
   PVOID PrivateHandle
);
````


## -parameters

### -param DeviceHandle 

A handle to the graphics device.


### -param PrivateHandle 

A handle to the graphics device.


## -returns
Return STATUS_SUCCESS if the call succeeds.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h</dt>
</dl>
</td>
</tr>
</table>