---
UID: NC:d3dkmddi.DXGKDDI_RESETFROMTIMEOUT
title: DXGKDDI_RESETFROMTIMEOUT
author: windows-driver-content
description: The DxgkDdiResetFromTimeout function resets the graphics processing unit (GPU) after a hardware timeout occurs and guarantees that the GPU is not writing or reading any memory by the time that DxgkDdiResetFromTimeout returns.
old-location: display\dxgkddiresetfromtimeout.htm
old-project: display
ms.assetid: b9bfc801-33f6-4911-ab7d-8e3c99a5e2e9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_RESETFROMTIMEOUT, DmFunctions_de82b888-dc3d-40b6-a3c3-360254efb972.xml, DxgkDdiResetFromTimeout, DxgkDdiResetFromTimeout callback function [Display Devices], d3dkmddi/DxgkDdiResetFromTimeout, display.dxgkddiresetfromtimeout
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
-	DxgkDdiResetFromTimeout
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_RESETFROMTIMEOUT callback function
The <i>DxgkDdiResetFromTimeout</i> function resets the graphics processing unit (GPU) after a hardware timeout occurs and guarantees that the GPU is not writing or reading any memory by the time that <i>DxgkDdiResetFromTimeout</i> returns.

## Syntax

```
DXGKDDI_RESETFROMTIMEOUT DxgkddiResetfromtimeout;

NTSTATUS DxgkddiResetfromtimeout(
  IN_CONST_HANDLE hAdapter
)
{...}
```

## Parameters

`hAdapter`

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


## Return Value

<i>DxgkDdiResetFromTimeout</i> returns STATUS_SUCCESS to indicate that the driver handled the call successfully; otherwise, the operating system bug checks and causes a restart.

## Remarks

The GPU scheduler calls <i>DxgkDdiResetFromTimeout</i> when it detects that a hardware time-out occurred. The time-out is typically a delayed response to a preempt request. <i>DxgkDdiResetFromTimeout</i> should reset the GPU. 

For more information about time-outs in this situation, see <a href="https://msdn.microsoft.com/3690ad06-002a-4939-9b04-b87245678464">Thread Synchronization and TDR</a>.

<i>DxgkDdiResetFromTimeout</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_releaseswizzlingrange.md">DxgkDdiReleaseSwizzlingRange</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_restartfromtimeout.md">DxgkDdiRestartFromTimeout</a>