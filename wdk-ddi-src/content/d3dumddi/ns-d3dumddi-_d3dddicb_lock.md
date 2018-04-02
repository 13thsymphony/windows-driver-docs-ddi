---
UID: NS:d3dumddi._D3DDDICB_LOCK
title: "_D3DDDICB_LOCK"
author: windows-driver-content
description: The D3DDDICB_LOCK structure describes parameters for locking an allocation.
old-location: display\d3dddicb_lock.htm
old-project: display
ms.assetid: e8d563fe-937a-48cb-9c7b-f282d12a9fcf
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDICB_LOCK, D3DDDICB_LOCK structure [Display Devices], D3D_param_Structs_84ac7e9c-e228-4ace-9e1b-74af8c52af85.xml, _D3DDDICB_LOCK, d3dumddi/D3DDDICB_LOCK, display.d3dddicb_lock
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dumddi.h
api_name:
-	D3DDDICB_LOCK
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_LOCK
---

# _D3DDDICB_LOCK structure
The D3DDDICB_LOCK structure describes parameters for locking an allocation.

## Syntax
```
typedef struct _D3DDDICB_LOCK {
  D3DKMT_HANDLE          hAllocation;
  UINT                   PrivateDriverData;
  UINT                   NumPages;
  CONST UINT             *pPages;
  VOID                   *pData;
  D3DDDICB_LOCKFLAGS     Flags;
  D3DGPU_VIRTUAL_ADDRESS GpuVirtualAddress;
} D3DDDICB_LOCK;
```

## Members


`hAllocation`

[in/out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation. The Microsoft Direct3D runtime's <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function returns this handle. Therefore, the user-mode display driver should use this handle to lock the allocation.

If the <b>Discard</b> bit-field flag is set in the <b>Flags</b> member, the video memory manager creates a new instance of the allocation and returns a new handle that represents the new instance.

`PrivateDriverData`

[in] Private data (for example, MIP level) that is sent from the user-mode display driver to the display miniport driver's <a href="https://msdn.microsoft.com/f861e055-70db-4e0a-9c62-87e2d41f92ae">DxgkDdiAcquireSwizzlingRange</a> function.

`NumPages`

[in] The number of pages in the page list that is pointed to by <b>pPages</b>.

`pPages`

[in] An array of pages to lock. Each page in the array is described by an integer offset. Zero means the first page in the surface, one means the second, and so on.

`pData`

[out] A pointer to the memory that is returned from the display miniport driver and memory manager. When locking a memory page list, the pointer that is returned is a pointer to the first memory page.

`Flags`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544214">D3DDDICB_LOCKFLAGS</a> structure that identifies, in bit-field flags, how to lock the allocation.

Note that specifying some flags together is invalid and that some flags depend on other flags. For more information about specifying these flags, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544214">D3DDDICB_LOCKFLAGS</a>.

`GpuVirtualAddress`

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544214">D3DDDICB_LOCKFLAGS</a>



<a href="https://msdn.microsoft.com/f861e055-70db-4e0a-9c62-87e2d41f92ae">DxgkDdiAcquireSwizzlingRange</a>



<a href="https://msdn.microsoft.com/69022797-432a-410b-8cbf-e1ef7111e7ea">pfnLockCb</a>