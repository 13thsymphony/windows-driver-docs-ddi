---
UID: NC:d3dkmddi.DXGKDDI_QUERYENGINESTATUS
title: DXGKDDI_QUERYENGINESTATUS
author: windows-driver-content
description: The display port driver's GPU scheduler calls this function to determine the progress of a node within an active physical display adapter (engine).
old-location: display\dxgkddiqueryenginestatus.htm
old-project: display
ms.assetid: 87c99fcb-d25a-41b1-a1f3-9cf9ab7b141e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_QUERYENGINESTATUS, DxgkDdiQueryEngineStatus, DxgkDdiQueryEngineStatus callback function [Display Devices], d3dkmddi/DxgkDdiQueryEngineStatus, display.dxgkddiqueryenginestatus
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
-	DxgkDdiQueryEngineStatus
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_QUERYENGINESTATUS callback function
The display port driver's GPU scheduler calls this function to determine the progress of a node within an active physical display adapter (engine).

## Syntax

```
DXGKDDI_QUERYENGINESTATUS DxgkddiQueryenginestatus;

NTSTATUS DxgkddiQueryenginestatus(
  IN_CONST_HANDLE hAdapter,
  INOUT_PDXGKARG_QUERYENGINESTATUS pQueryEngineStatus
)
{...}
```

## Parameters

`hAdapter`

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`pQueryEngineStatus`

A pointer to a   <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryenginestatus.md">DXGKARG_QUERYENGINESTATUS</a> structure that specifies a node and physical adapter that are to be queried for progress, and that supplies a value for the progress.


## Return Value

Returns STATUS_SUCCESS if the function succeeds. Otherwise, this function returns one of the error codes defined in Ntstatus.h.

## Remarks

This function should be made pageable, and it should always succeed.

The operating system guarantees that this function follows the first level synchronization mode as defined in <a href="https://msdn.microsoft.com/9fce6a18-2a66-4518-b05b-e85bdaa3951f">Threading and Synchronization First Level</a>.

For more information, see <a href="https://msdn.microsoft.com/5BC4F94C-2B45-44E2-8BBF-B455BB864A29">TDR changes in Windows 8</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_queryenginestatus.md">DXGKARG_QUERYENGINESTATUS</a>