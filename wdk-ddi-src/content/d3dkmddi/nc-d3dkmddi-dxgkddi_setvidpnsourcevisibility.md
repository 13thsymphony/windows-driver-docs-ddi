---
UID: NC:d3dkmddi.DXGKDDI_SETVIDPNSOURCEVISIBILITY
title: DXGKDDI_SETVIDPNSOURCEVISIBILITY
author: windows-driver-content
description: The DxgkDdiSetVidPnSourceVisibility function programs the video output codec that is associated with a specified video present source to either start scanning or stop scanning the source's primary surface.
old-location: display\dxgkddisetvidpnsourcevisibility.htm
old-project: display
ms.assetid: c94473b4-b898-456d-944d-8879adea16d1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGKDDI_SETVIDPNSOURCEVISIBILITY, DmFunctions_6a3bb1aa-8bc1-4672-8028-ea3299809a37.xml, DxgkDdiSetVidPnSourceVisibility, DxgkDdiSetVidPnSourceVisibility callback function [Display Devices], d3dkmddi/DxgkDdiSetVidPnSourceVisibility, display.dxgkddisetvidpnsourcevisibility
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
-	DxgkDdiSetVidPnSourceVisibility
product: Windows
targetos: Windows
req.typenames: DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_SETVIDPNSOURCEVISIBILITY callback function
The <i>DxgkDdiSetVidPnSourceVisibility</i> function programs the video output codec that is associated with a specified video present source to either start scanning or stop scanning the source's primary surface.

## Syntax

```
DXGKDDI_SETVIDPNSOURCEVISIBILITY DxgkddiSetvidpnsourcevisibility;

NTSTATUS DxgkddiSetvidpnsourcevisibility(
  IN_CONST_HANDLE hAdapter,
  IN_CONST_PDXGKARG_SETVIDPNSOURCEVISIBILITY pSetVidPnSourceVisibility
)
{...}
```

## Parameters

`hAdapter`

A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

`pSetVidPnSourceVisibility`

A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_setvidpnsourcevisibility.md">DXGKARG_SETVIDPNSOURCEVISIBILITY</a> structure that contains function arguments.


## Return Value

<i>DxgkDdiSetVidPnSourceVisibility </i>returns STATUS_SUCCESS if it succeeds; otherwise, it returns one of the error codes defined in <i>Ntstatus.h</i>.

## Remarks

See requirements on calling this function with multiplane overlays in <a href="https://msdn.microsoft.com/BAD7FD48-905D-4547-8C69-133240B39FA3">Multiplane overlay VidPN presentation</a>.

<i>DxgkDdiSetVidPnSourceVisibility</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dkmddi.h |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/488c929b-3816-457f-b5c2-c176b93d5546">DxgkDdiSetVidPnSourceAddress</a>