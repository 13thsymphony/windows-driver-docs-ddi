---
UID : NC:d3dkmddi.DXGKDDI_CLOSEALLOCATION
title : DXGKDDI_CLOSEALLOCATION
author : windows-driver-content
description : The DxgkDdiCloseAllocation function unbinds device-specific allocations that the DxgkDdiOpenAllocation function created.
old-location : display\dxgkddicloseallocation.htm
old-project : display
ms.assetid : f9c195d7-debe-495e-a355-e176d06884f8
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
req.alt-api : DxgkDdiCloseAllocation
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


# DXGKDDI_CLOSEALLOCATION function
The <i>DxgkDdiCloseAllocation</i> function unbinds device-specific allocations that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a> function created.

## Syntax

```
DXGKDDI_CLOSEALLOCATION DxgkddiCloseallocation;

NTSTATUS DxgkddiCloseallocation(
  IN_CONST_HANDLE hDevice,
  IN_CONST_PDXGKARG_CLOSEALLOCATION pCloseAllocation
)
{...}
```

## Parameters

`hDevice`

[in] A handle to the graphics context device that allocations are unbound from. The display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a> function previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <b>hDevice</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a> structure.

`pCloseAllocation`

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_closeallocation.md">DXGKARG_CLOSEALLOCATION</a> structure that contains information about unbinding allocations.


## Return Value

<i>DxgkDdiCloseAllocation</i> returns STATUS_SUCCESS, or an appropriate error result if the allocations are not successfully unbound from the graphics context device.

## Remarks

Before the display miniport driver receives a call to its <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyallocation.md">DxgkDdiDestroyAllocation</a> function to release allocations, the driver calls the <i>DxgkDdiCloseAllocation</i> function to close all bindings to those allocations. 

For a resource that contains multiple allocations, the DirectX graphics kernel subsystem directs <i>DxgkDdiCloseAllocation</i> to simultaneously close all of the allocations by specifying the handles to the device-specific allocations in the <b>pOpenHandleList</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_closeallocation.md">DXGKARG_CLOSEALLOCATION</a> structure. 

<i>DxgkDdiCloseAllocation</i> should be made pageable.

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
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_closeallocation.md">DXGKARG_CLOSEALLOCATION</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createdevice.md">DXGKARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyallocation.md">DxgkDdiDestroyAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_openallocationinfo.md">DxgkDdiOpenAllocation</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_CLOSEALLOCATION callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>