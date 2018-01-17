---
UID: NS:d3dkmddi._DXGKARG_DESTROYALLOCATION
title: _DXGKARG_DESTROYALLOCATION
author: windows-driver-content
description: The DXGKARG_DESTROYALLOCATION structure describes how the display miniport driver should release allocations.
old-location: display\dxgkarg_destroyallocation.htm
old-project: display
ms.assetid: 0679ade4-9bbd-4bbc-ad2a-46bf35cac645
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGKARG_DESTROYALLOCATION, DXGKARG_DESTROYALLOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARG_DESTROYALLOCATION
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
req.typenames: DXGKARG_DESTROYALLOCATION
---

# _DXGKARG_DESTROYALLOCATION structure



## -description
The DXGKARG_DESTROYALLOCATION structure describes how the display miniport driver should release allocations.



## -syntax

````
typedef struct _DXGKARG_DESTROYALLOCATION {
  UINT                        NumAllocations;
  const HANDLE                *pAllocationList;
  HANDLE                      hResource;
  DXGK_DESTROYALLOCATIONFLAGS Flags;
} DXGKARG_DESTROYALLOCATION;
````


## -struct-fields

### -field NumAllocations

[in] The number of elements in the array that <b>pAllocationList</b> specifies, which represents the number of allocations to release.


### -field pAllocationList

[in] An array of handles to the allocations to release.


### -field hResource

[in/out] A handle to a resource. The display miniport driver cleans up this handle if it must release the resource along with the allocations.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_destroyallocationflags.md">DXGK_DESTROYALLOCATIONFLAGS</a> structure that identifies how to release the allocations.


## -remarks
The handles in the array that the <b>pAllocationList</b> member specifies are handles to allocations that the driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a> function previously returned in the <b>hAllocation</b> members of <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a> structures, which are part of the <a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a> structure's <b>pAllocationInfo</b> member. Each allocation handle points to a buffer that contains private driver data for the allocation. The display miniport driver must release the memory for the allocations during the call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyallocation.md">DxgkDdiDestroyAllocation</a>. 


## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_destroyallocation.md">DxgkDdiDestroyAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_destroyallocationflags.md">DXGK_DESTROYALLOCATIONFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgkarg_createallocation.md">DXGKARG_CREATEALLOCATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_DESTROYALLOCATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

