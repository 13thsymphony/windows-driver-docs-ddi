---
UID : NC:d3dkmddi.DXGKDDI_FLIPOVERLAY
title : DXGKDDI_FLIPOVERLAY
author : windows-driver-content
description : The DxgkDdiFlipOverlay function displays a new allocation by using the specified overlay.
old-location : display\dxgkddiflipoverlay.htm
old-project : display
ms.assetid : 9e35a48b-1741-4ee2-8e15-6ce51ad4c0ad
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dkmddi.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DxgkDdiFlipOverlay
req.alt-loc : d3dkmddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : PASSIVE_LEVEL
req.typenames : DD_MULTISAMPLEQUALITYLEVELSDATA
---


# DXGKDDI_FLIPOVERLAY function
The <i>DxgkDdiFlipOverlay</i> function displays a new allocation by using the specified overlay.

## Syntax

```
DXGKDDI_FLIPOVERLAY DxgkddiFlipoverlay;

NTSTATUS DxgkddiFlipoverlay(
  IN_CONST_HANDLE hOverlay,
  IN_CONST_PDXGKARG_FLIPOVERLAY pFlipOverlay
)
{...}
```

## Parameters

`hOverlay`

[in] A handle to the overlay to be flipped. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hOverlay</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createoverlay.md">DXGKARG_CREATEOVERLAY</a> structure.

`pFlipOverlay`

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_flipoverlay.md">DXGKARG_FLIPOVERLAY</a> structure that describes the new allocation to display by using the overlay.


## Return Value

<i>DxgkDdiFlipOverlay</i> returns one of the following values:
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><i>DxgkDdiFlipOverlay</i> successfully displays the new allocation.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters that were passed to <i>DxgkDdiFlipOverlay</i> contained errors that prevented it from completing.
<dl>
<dt><b>STATUS_NO_MEMORY</b></dt>
</dl><i>DxgkDdiFlipOverlay</i> could not allocate memory that was required for it to complete.
<dl>
<dt><b>STATUS_GRAPHICS_DRIVER_MISMATCH</b></dt>
</dl>The display miniport driver is not compatible with the user-mode display driver that initiated the call to <i>DxgkDdiFlipOverlay</i>.

## Remarks

<i>DxgkDdiFlipOverlay</i> should be made pageable.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3dkmddi.h |
| **Library** |  |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createoverlay.md">DXGKARG_CREATEOVERLAY</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_flipoverlay.md">DXGKARG_FLIPOVERLAY</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createoverlay.md">DxgkDdiCreateOverlay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_FLIPOVERLAY callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>