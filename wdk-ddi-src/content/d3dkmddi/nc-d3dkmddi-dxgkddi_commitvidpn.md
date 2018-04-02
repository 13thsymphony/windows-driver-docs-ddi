---
UID: NC:d3dkmddi.DXGKDDI_COMMITVIDPN
title: DXGKDDI_COMMITVIDPN
author: windows-driver-content
description: The DxgkDdiCommitVidPn function makes a specified video present network (VidPN) active on a display adapter.
old-location: display\dxgkddicommitvidpn.htm
old-project: display
ms.assetid: 979b86e9-f3ff-4022-8c00-b6afc2b1f747
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGKDDI_COMMITVIDPN, DmFunctions_467cba1e-3eeb-4735-9fb3-46c8c737b48d.xml, DxgkDdiCommitVidPn, DxgkDdiCommitVidPn callback function [Display Devices], d3dkmddi/DxgkDdiCommitVidPn, display.dxgkddicommitvidpn
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	DxgkDdiCommitVidPn
product:
- Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_COMMITVIDPN callback function
The <i>DxgkDdiCommitVidPn</i> function makes a specified video present network (VidPN) active on a display adapter.

## Syntax

```
DXGKDDI_COMMITVIDPN DxgkddiCommitvidpn;

NTSTATUS DxgkddiCommitvidpn(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_COMMITVIDPN_CONST pCommitVidPn
)
{...}
```

## Parameters

`hAdapter`

A handle to a context block associated with a display adapter. The display miniport driver previously provided this handle to the DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a> function.

`pCommitVidPn`




## Return Value

<i>DxgkDdiCommitVidPn</i> returns one of the values in the following list. The VidPN referred to in the list is the VidPN represented by <i>pCommitVidPnArg</i>-&gt;<b>hFunctionalVidPn</b>.

## Remarks

For more information about how the display miniport driver should handle calls to <i>DxgkDdiCommitVidPn</i>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff557552">DXGKARG_COMMITVIDPN</a>.

Beginning with Windows 8, if the display miniport driver sets the <b>SupportSmoothRotation</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a> structure, it must support updating the path rotation on the adapter using the <a href="https://msdn.microsoft.com/3bf5ebf7-8113-4ab2-beb1-1a52df25ac37">DxgkDdiUpdateActiveVidPnPresentPath</a> function. The driver must always be able to set the path rotation during a call to the <i>DxgkDdiCommitVidPn</i> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557552">DXGKARG_COMMITVIDPN</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>



<a href="https://msdn.microsoft.com/5fd4046f-54c3-4dfc-8d51-0d9ebcde0bea">DxgkDdiAddDevice</a>



<a href="https://msdn.microsoft.com/3bf5ebf7-8113-4ab2-beb1-1a52df25ac37">DxgkDdiUpdateActiveVidPnPresentPath</a>