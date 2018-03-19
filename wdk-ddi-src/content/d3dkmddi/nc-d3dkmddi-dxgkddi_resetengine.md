---
UID: NC:d3dkmddi.DXGKDDI_RESETENGINE
title: DXGKDDI_RESETENGINE
author: windows-driver-content
description: The display port driver's GPU scheduler calls this function to reset an active node on a physical display adapter when the scheduler detects a timeout condition on the adapter.
old-location: display\dxgkddiresetengine.htm
old-project: display
ms.assetid: 9c2097b2-5742-422c-a650-7efff2484970
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_RESETENGINE, DxgkDdiResetEngine, DxgkDdiResetEngine callback function [Display Devices], d3dkmddi/DxgkDdiResetEngine, display.dxgkddiresetengine
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3dkmddi.h
api_name:
-	DxgkDdiResetEngine
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_RESETENGINE callback function
The display port driver's GPU scheduler calls this function to reset an active node on a physical display adapter when the scheduler detects a timeout condition on the adapter.

## Syntax

```
DXGKDDI_RESETENGINE DxgkddiResetengine;

NTSTATUS DxgkddiResetengine(
  IN_CONST_HANDLE hAdapter,
  INOUT_PDXGKARG_RESETENGINE pResetEngine
)
{...}
```

## Parameters

`hAdapter`

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`pResetEngine`

A value of type  <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_resetengine.md">DXGKARG_RESETENGINE</a> that specifies nodes that are to be reset and supplies a fence identifier for the last aborted packet.


## Return Value

Returns <b>STATUS_SUCCESS</b> if the function succeeds. Otherwise, this function returns one of the error codes defined in Ntstatus.h.

## Remarks

The display miniport driver should return from a call to this function only when the reset operation is completed, nothing remains in the physical adapter's hardware queue, and the specified nodes are ready to accept new packets.

 This function should be made pageable.

The operating system guarantees that this function follows the first level synchronization mode as defined in <a href="https://msdn.microsoft.com/9fce6a18-2a66-4518-b05b-e85bdaa3951f">Threading and Synchronization First Level</a>.

For more information, see  <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_resetengine.md">DXGKARG_RESETENGINE</a>