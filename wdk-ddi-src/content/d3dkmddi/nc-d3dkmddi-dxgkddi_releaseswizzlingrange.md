---
UID: NC:d3dkmddi.DXGKDDI_RELEASESWIZZLINGRANGE
title: DXGKDDI_RELEASESWIZZLINGRANGE function
author: windows-driver-content
description: The DxgkDdiReleaseSwizzlingRange function releases a swizzling range that the DxgkDdiAcquireSwizzlingRange function previously set up.
old-location: display\dxgkddireleaseswizzlingrange.htm
old-project: display
ms.assetid: 6c583a48-baa4-429f-b2fc-5f86859617cc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGKDDI_RELEASESWIZZLINGRANGE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkDdiReleaseSwizzlingRange
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
req.typenames: D3D12DDI_WRITEBUFFERIMMEDIATE_PARAMETER_0032
---

# DXGKDDI_RELEASESWIZZLINGRANGE function



## -description
The <i>DxgkDdiReleaseSwizzlingRange</i> function releases a swizzling range that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function previously set up.



## -syntax

````
DXGKDDI_RELEASESWIZZLINGRANGE DxgkDdiReleaseSwizzlingRange;

NTSTATUS APIENTRY DxgkDdiReleaseSwizzlingRange(
  _In_ const HANDLE                        hAdapter,
  _In_ const DXGKARG_RELEASESWIZZLINGRANGE *pReleaseSwizzlingRange
)
{ ... }
````


## -parameters

### -param hAdapter [in]

[in] A handle to a context block that is associated with a display adapter. The display miniport driver previously provided this handle to the Microsoft DirectX graphics kernel subsystem in the <i>MiniportDeviceContext</i> output parameter of the <a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a> function.


### -param pReleaseSwizzlingRange [in]

[in] A pointer to a <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_releaseswizzlingrange.md">DXGKARG_RELEASESWIZZLINGRANGE</a> structure that contains information for releasing the swizzling range.


## -returns
<i>DxgkDdiReleaseSwizzlingRange</i> returns STATUS_SUCCESS, or an appropriate error result if the swizzling range is not successfully released.


## -remarks
The <i>DxgkDdiReleaseSwizzlingRange</i> function is typically called when the specified allocation (that is, the <b>hAllocation</b> member of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_releaseswizzlingrange.md">DXGKARG_RELEASESWIZZLINGRANGE</a> structure that the <i>pReleaseSwizzlingRange</i> parameter points to) is evicted or destroyed, or when another allocation requires the swizzling range that the <b>RangeId</b> member of DXGKARG_RELEASESWIZZLINGRANGE specifies.

If the specified allocation is currently associated with multiple swizzling ranges (through calls to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function), the display miniport driver should release only the swizzling range that the <b>RangeId</b> member of DXGKARG_RELEASESWIZZLINGRANGE specifies. If the display miniport driver releases all of the swizzling ranges that are associated with the allocation, random corruption in the allocation might result because an application might currently be using one or more of the swizzling ranges.

The driver must use memory-mapped I/O (MMIO) to set up a swizzling range. These swizzling-range accesses must not interfere with the execution of the GPU (that is, the GPU must not be idle when <i>DxgkDdiReleaseSwizzlingRange</i> is called). 

All calls to <i>DxgkDdiReleaseSwizzlingRange</i> are serialized among themselves but not with any other device driver interface (DDI) function.

<i>DxgkDdiReleaseSwizzlingRange</i> should be made pageable.


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_releaseswizzlingrange.md">DXGKARG_RELEASESWIZZLINGRANGE</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a>
</dt>
<dt>
<a href="..\dispmprt\nc-dispmprt-dxgkddi_add_device.md">DxgkDdiAddDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKDDI_RELEASESWIZZLINGRANGE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

