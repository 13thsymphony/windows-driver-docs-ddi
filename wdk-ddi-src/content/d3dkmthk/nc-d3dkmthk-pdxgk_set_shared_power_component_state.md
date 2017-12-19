---
UID: NC.d3dkmthk.PDXGK_SET_SHARED_POWER_COMPONENT_STATE
title: PDXGK_SET_SHARED_POWER_COMPONENT_STATE
author: windows-driver-content
description: A callback to indicate whether the specified power component is active.
old-location: display\pdxgk_set_shared_power_component_state.htm
old-project: display
ms.assetid: 779072A4-A82B-4251-93F5-5B6C7ED0598E
ms.author: windowsdriverdev
ms.date: 12/15/2017
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
req.alt-api: PDXGK_SET_SHARED_POWER_COMPONENT_STATE
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

# PDXGK_SET_SHARED_POWER_COMPONENT_STATE callback



## -description
A callback to indicate whether the specified power component is active.



## -prototype

````
NTSTATUS PDXGK_SET_SHARED_POWER_COMPONENT_STATE(
   PVOID GraphicsDeviceHandle,
   PVOID GraphicsDeviceHandle,
   ULONG GraphicsDeviceHandle
);
````


## -parameters

### -param GraphicsDeviceHandle 

A handle to the graphics device.


### -param GraphicsDeviceHandle 

A handle to the graphics device.


### -param GraphicsDeviceHandle 

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