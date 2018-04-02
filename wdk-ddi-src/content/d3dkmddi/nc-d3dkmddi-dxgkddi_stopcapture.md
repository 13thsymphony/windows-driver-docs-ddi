---
UID: NC:d3dkmddi.DXGKDDI_STOPCAPTURE
title: DXGKDDI_STOPCAPTURE
author: windows-driver-content
description: The DxgkDdiStopCapture function stops the capture hardware from using the given allocation as a capture buffer.
old-location: display\dxgkddistopcapture.htm
old-project: display
ms.assetid: e5d622cc-c550-44cf-8923-5092226066d9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_STOPCAPTURE, DmFunctions_108ab359-fe5b-46f2-bc1b-f1f91bd5b327.xml, DxgkDdiStopCapture, DxgkDdiStopCapture callback function [Display Devices], d3dkmddi/DxgkDdiStopCapture, display.dxgkddistopcapture
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dkmddi.h
api_name:
-	DxgkDdiStopCapture
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_STOPCAPTURE callback function
The <i>DxgkDdiStopCapture</i> function stops the capture hardware from using the given allocation as a capture buffer.

## Syntax

```
DXGKDDI_STOPCAPTURE DxgkddiStopcapture;

NTSTATUS DxgkddiStopcapture(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_STOPCAPTURE pStopCapture
)
{...}
```

## Parameters

`hAdapter`

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.

`pStopCapture`

[in] A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff559488">DXGKARG_STOPCAPTURE</a> structure that contains the handle to the allocation that is used as a capture buffer.


## Return Value

<i>DxgkDdiStopCapture</i> returns STATUS_SUCCESS, or an appropriate error result if the allocation is not successfully stopped.

## Remarks

When a capture buffer is destroyed, the DirectX graphics kernel subsystem calls the <i>DxgkDdiStopCapture</i> function to inform the display miniport driver to stop the capture hardware from using the allocation as the capture buffer. If the capture hardware already stopped using the allocation, the driver should ignore the call.

<i>DxgkDdiStopCapture</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559488">DXGKARG_STOPCAPTURE</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>