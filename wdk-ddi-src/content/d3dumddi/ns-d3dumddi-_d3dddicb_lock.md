---
UID: NS.D3DUMDDI._D3DDDICB_LOCK
title: _D3DDDICB_LOCK
author: windows-driver-content
description: The D3DDDICB_LOCK structure describes parameters for locking an allocation.
old-location: display\d3dddicb_lock.htm
old-project: display
ms.assetid: e8d563fe-937a-48cb-9c7b-f282d12a9fcf
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDICB_LOCK, D3DDDICB_LOCK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDICB_LOCK
req.alt-loc: d3dumddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
---

# _D3DDDICB_LOCK structure



## -description
The D3DDDICB_LOCK structure describes parameters for locking an allocation. 



## -syntax

````
typedef struct _D3DDDICB_LOCK {
  D3DKMT_HANDLE          hAllocation;
  UINT                   PrivateDriverData;
  UINT                   NumPages;
  const UINT             *pPages;
  VOID                   *pData;
  D3DDDICB_LOCKFLAGS     Flags;
#if D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7
  D3DGPU_VIRTUAL_ADDRESS GpuVirtualAddress;
#endif 
} D3DDDICB_LOCK;
````


## -struct-fields

### -field hAllocation

[in/out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation. The Microsoft Direct3D runtime's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function returns this handle. Therefore, the user-mode display driver should use this handle to lock the allocation.

If the <b>Discard</b> bit-field flag is set in the <b>Flags</b> member, the video memory manager creates a new instance of the allocation and returns a new handle that represents the new instance.


### -field PrivateDriverData

[in] Private data (for example, MIP level) that is sent from the user-mode display driver to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a> function.


### -field NumPages

[in] The number of pages in the page list that is pointed to by <b>pPages</b>.


### -field pPages

[in] An array of pages to lock. Each page in the array is described by an integer offset. Zero means the first page in the surface, one means the second, and so on.


### -field pData

[out] A pointer to the memory that is returned from the display miniport driver and memory manager. When locking a memory page list, the pointer that is returned is a pointer to the first memory page.


### -field Flags

[in] A <a href="display.d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a> structure that identifies, in bit-field flags, how to lock the allocation.

Note that specifying some flags together is invalid and that some flags depend on other flags. For more information about specifying these flags, see the Remarks section of <a href="display.d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a>.


### -field GpuVirtualAddress

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## -remarks


## -requirements
<table>
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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dddicb_lockflags">D3DDDICB_LOCKFLAGS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_acquireswizzlingrange.md">DxgkDdiAcquireSwizzlingRange</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockcb.md">pfnLockCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDICB_LOCK structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

