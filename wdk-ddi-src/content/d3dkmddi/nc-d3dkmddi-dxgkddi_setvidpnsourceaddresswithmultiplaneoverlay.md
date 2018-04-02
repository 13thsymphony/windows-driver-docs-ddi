---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
title: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY
author: windows-driver-content
description: Sets the addresses of multiple surfaces, including the Desktop Window Manager (DWM)'s swapchain, that are associated with a particular video present source. This function is used to present multiple surfaces (including the DWM’s swapchain) to the screen.
old-location: display\dxgkddisetvidpnsourceaddresswithmultiplaneoverlay.htm
old-project: display
ms.assetid: 95108e45-1a3a-4a75-8719-0caadb911469
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay, DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay callback function [Display Devices], d3dkmddi/DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay, display.dxgkddisetvidpnsourceaddresswithmultiplaneoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
req.irql: PROFILE_LEVEL  - 1
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3dkmddi.h
api_name:
-	DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY callback function
Sets the addresses of multiple surfaces, including the Desktop Window Manager (DWM)'s swapchain, that are associated with a particular video present source. This function is used to present multiple surfaces (including the DWM’s swapchain) to the screen.

## Syntax

```
DXGKDDI_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY DxgkddiSetvidpnsourceaddresswithmultiplaneoverlay;

NTSTATUS DxgkddiSetvidpnsourceaddresswithmultiplaneoverlay(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY pSetVidPnSourceAddressWithMultiPlaneOverlay
)
{...}
```

## Parameters

`hAdapter`

A handle to a context block that is associated with a display adapter.

The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.

`pSetVidPnSourceAddressWithMultiPlaneOverlay`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh780296">DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY</a> structure that defines multiplane overlays that are enabled for  display.


## Return Value

Returns <b>STATUS_SUCCESS</b> if it succeeds; otherwise it returns one of the error codes defined in Ntstatus.h.

## Remarks

See requirements on calling this function in <a href="https://msdn.microsoft.com/BAD7FD48-905D-4547-8C69-133240B39FA3">Multiplane overlay VidPN presentation</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PROFILE_LEVEL  - 1 |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh780296">DXGKARG_SETVIDPNSOURCEADDRESSWITHMULTIPLANEOVERLAY</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>