---
UID: NC:d3d12umddi.PFND3D12DDI_OPENADAPTER
title: PFND3D12DDI_OPENADAPTER
author: windows-driver-content
description: The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls.
old-location: display\pfnd3d12ddi_openadapter.htm
old-project: display
ms.assetid: FEDC2FB5-9F1A-4829-A98D-3BEA4218AE3D
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D12DDI_OPENADAPTER, PFND3D12DDI_OPENADAPTER callback function [Display Devices], d3d12umddi/PFND3D12DDI_OPENADAPTER, display.pfnd3d12ddi_openadapter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_OPENADAPTER
product:
- Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---


# PFND3D12DDI_OPENADAPTER callback function
The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls.

## Syntax

```
PFND3D12DDI_OPENADAPTER Pfnd3d12ddiOpenadapter;

HRESULT Pfnd3d12ddiOpenadapter(
  D3D12DDIARG_OPENADAPTER *
)
{...}
```

## Parameters

`*`




## Return Value

PFND3D12DDI_OPENADAPTER returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter object was successfully created.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

                PFND3D12DDI_OPENADAPTER could not allocate memory that was required for it to complete.

</td>
</tr>
</table>

## Remarks

The graphics adapter object that is created by the PFND3D12DDI_OPENADAPTER function represents the underlying graphics hardware. Before the Direct3D runtime can create a display device by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt779070">PFND3D12DDI_CREATEDEVICE_0003</a>, the user-mode display driver should call the <a href="https://msdn.microsoft.com/8008574f-a89e-4fed-b745-7cf5baa68e64">pfnQueryAdapterInfoCb</a> function to query for the graphics hardware capabilities from the display miniport driver. 

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | d3d12umddi.h |