---
UID: NE.d3dumddi._D3DDDI_DEVICEEXECUTION_STATE
title: _D3DDDI_DEVICEEXECUTION_STATE
author: windows-driver-content
description: Indicates the state of the device.
old-location: display\d3dddi_deviceexecution_state.htm
old-project: display
ms.assetid: E81A31B5-E06F-4848-9AC6-8A18E8E97E15
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDI_DEVICEEXECUTION_STATE, D3DDDI_DEVICEEXECUTION_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_DEVICEEXECUTION_STATE
req.alt-loc: D3dumddi.h
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

# _D3DDDI_DEVICEEXECUTION_STATE enumeration



## -description
Indicates the state of the device.



## -syntax

````
typedef enum _D3DDDI_DEVICEEXECUTION_STATE { 
  D3DDDI_DEVICEEXECUTION_ACTIVE             = 1,
  D3DDDI_DEVICEEXECUTION_RESET              = 2,
  D3DDDI_DEVICEEXECUTION_HUNG               = 3,
  D3DDDI_DEVICEEXECUTION_STOPPED            = 4,
  D3DDDI_DEVICEEXECUTION_ERROR_OUTOFMEMORY  = 5,
  D3DDDI_DEVICEEXECUTION_ERROR_DMAFAULT     = 6
} D3DDDI_DEVICEEXECUTION_STATE;
````


## -enum-fields

### -field D3DDDI_DEVICEEXECUTION_ACTIVE

The device is active.


### -field D3DDDI_DEVICEEXECUTION_RESET

The device has been reset.


### -field D3DDDI_DEVICEEXECUTION_HUNG

The device is still running but has stopped responding (it is "hung").


### -field D3DDDI_DEVICEEXECUTION_STOPPED

The device has stopped.


### -field D3DDDI_DEVICEEXECUTION_ERROR_OUTOFMEMORY

The device has run out of memory.


### -field D3DDDI_DEVICEEXECUTION_ERROR_DMAFAULT

The device has a DMA fault error.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>