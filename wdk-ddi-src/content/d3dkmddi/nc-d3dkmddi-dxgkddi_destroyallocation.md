---
UID: NC.d3dkmddi.DXGKDDI_DESTROYALLOCATION
title: DXGKDDI_DESTROYALLOCATION
author: windows-driver-content
description: The DxgkDdiDestroyAllocation function releases allocations.
old-location: display\dxgkddidestroyallocation.htm
old-project: display
ms.assetid: cade544a-f9c6-4635-ab57-d09d694ca315
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
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
req.alt-api: DxgkDdiDestroyAllocation
req.alt-loc: d3dkmddi.h
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
---

# DXGKDDI_DESTROYALLOCATION callback



## -description
The <i>DxgkDdiDestroyAllocation</i> function releases allocations.


## -prototype

````
PDXGKDDI_DESTROYALLOCATION DxgkDdiDestroyAllocation;

NTSTATUS APIENTRY DxgkDdiDestroyAllocation(
  _In_ const HANDLE                    hAdapter,
  _In_ const DXGKARG_DESTROYALLOCATION *pDestroyAllocation
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.

### -param pDestroyAllocation [in]

[in] A pointer to a <a href="display.dxgkarg_destroyallocation">DXGKARG_DESTROYALLOCATION</a> structure that contains information for releasing allocations.

## -returns
<i>DxgkDdiDestroyAllocation</i> returns STATUS_SUCCESS, or an appropriate error result if the allocations are not successfully released.

## -remarks
When the user-mode display driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> function, the DirectX graphics kernel subsystem (which is part of <i>Dxgkrnl.sys</i>) calls the display miniport driver's <i>DxgkDdiDestroyAllocation</i> function to release the allocations. The display miniport driver should clean up its internal data structures and references to the allocations. The Microsoft Direct3D runtime initiates calls to the video memory manager (which is also part of <i>Dxgkrnl.sys</i>), which then calls the GPU scheduler (which is also part of <i>Dxgkrnl.sys</i>) to synchronize before video memory is actually released. 

The display miniport driver can release the entire resource as well as allocations. To determine whether the resource should be released, the display miniport driver can check whether the <b>DestroyResource</b> flag is set in the <b>Flags</b> member of the <a href="display.dxgkarg_destroyallocation">DXGKARG_DESTROYALLOCATION</a> structure that the <i>pDestroyAllocation</i> parameter points to. To release the resource, the display miniport driver must clean up the handle that the <b>hResource</b> member of DXGKARG_DESTROYALLOCATION specifies. If the display miniport driver does not release the resource, the driver can change the value in <b>hResource</b> if necessary.

<i>DxgkDdiDestroyAllocation</i> should be made pageable.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgkarg_destroyallocation">DXGKARG_DESTROYALLOCATION</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PDXGKDDI_DESTROYALLOCATION callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
