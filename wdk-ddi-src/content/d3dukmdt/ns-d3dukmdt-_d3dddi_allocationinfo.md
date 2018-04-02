---
UID: NS:d3dukmdt._D3DDDI_ALLOCATIONINFO
title: "_D3DDDI_ALLOCATIONINFO"
author: windows-driver-content
description: The D3DDDI_ALLOCATIONINFO structure describes an allocation.
old-location: display\d3dddi_allocationinfo.htm
old-project: display
ms.assetid: 69181a7c-62bd-4df0-95fc-fe6c3ab14209
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_ALLOCATIONINFO, D3DDDI_ALLOCATIONINFO structure [Display Devices], D3D_other_Structs_5125c057-c4b7-45fd-b7d9-9ebcfce4fff7.xml, _D3DDDI_ALLOCATIONINFO, d3dukmdt/D3DDDI_ALLOCATIONINFO, display.d3dddi_allocationinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_ALLOCATIONINFO
product: Windows
targetos: Windows
req.typenames: D3DDDI_ALLOCATIONINFO
---

# _D3DDDI_ALLOCATIONINFO structure
The D3DDDI_ALLOCATIONINFO structure describes an allocation.

## Syntax
```
typedef struct _D3DDDI_ALLOCATIONINFO {
  D3DKMT_HANDLE                  hAllocation;
  CONST VOID                     *pSystemMem;
  VOID                           *pPrivateDriverData;
  UINT                           PrivateDriverDataSize;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  union {
    UINT Value;
    struct {
      UINT  : 1  Primary;
      UINT  : 1  Stereo;
      UINT  : 30 Reserved;
      UINT  : 31 Reserved;
    };
  } Flags;
} D3DDDI_ALLOCATIONINFO;
```

## Members


`hAllocation`

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the allocation. This kernel-mode allocation handle is associated with the kernel-mode resource handle (if non-<b>NULL</b>) that the Microsoft Direct3D runtime's <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function returns in the <b>hKMResource</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544137">D3DDDICB_ALLOCATE</a> structure. The user-mode display driver can use this kernel-mode allocation handle to reference the allocation in the command buffer.

`pSystemMem`

[in] A pointer to system memory that the Direct3D runtime preallocated. Otherwise, this member is <b>NULL</b> if the allocation is to use video memory. 

If the allocation is in system memory, the user-mode display driver should assign the buffer in the <b>pSysMem</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544651">D3DDDI_SURFACEINFO</a> structure for the resource to <b>pSystemMem</b>. This buffer is specified when the Direct3D runtime calls the user-mode display driver's <a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a> function to create resources.

`pPrivateDriverData`

[in/out] A pointer to buffer that contains optional private data that might be required by the display miniport driver to create the allocation. The display miniport driver can also return data in the buffer. When the contents of the buffer are passed to the display miniport driver, the contents must be in a format that the display miniport driver can process.

`PrivateDriverDataSize`

[in] The size, in bytes, of the block of private data that <b>pPrivateDriverData</b> points to.

`VidPnSourceId`

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology if the allocation is for the primary surface. The driver should set <b>VidPnSourceId</b> only for primary allocation types and not for any other type of allocation. If the driver sets <b>VidPnSourceId</b> for any other allocation type in a call to the <a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a> function, <b>pfnAllocateCb</b> returns D3DDDI_ID_NOTAPPLICABLE.

When the DirectX graphics kernel subsystem initiates the creation of the allocation for the shared primary surface, the display miniport driver can determine the identification number from the <b>VidPnSourceId</b> member of the <a href="https://msdn.microsoft.com/edf59add-0155-4619-9c7c-fdb63b954f85">D3DKMDDI_SHAREDPRIMARYSURFACEDATA</a> structure that the <b>pPrivateDriverData</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a> structure points to.

`Flags`

[in] A union that contains either a structure (with the first three members that are described in the following list) or a 32-bit value (in the <b>Value</b> member) that indentifies the type of allocation:



#### Value

[in] A 32-bit value that identifies the type of allocation.

## Remarks
When the user-mode display driver sets the <b>Primary</b> bit-field flag in the <b>Flags</b> member of D3DDDI_ALLOCATIONINFO, certain restrictions apply to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a> structure in the <b>pAllocationInfo</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a> structure for the allocation in a call to the display miniport driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function. These restrictions include the following: 

<ul>
<li>
The allocation is allocated according to preferences; otherwise, the allocation defaults to the supported write segment set, and all of the specified segments in the write segment set must be CPU-accessible.

</li>
<li>The display miniport driver cannot set the following bit-field flags in the  <b>Flags</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>:<ul>
<li><b>PermanentSysMem</b></li>
<li><b>Cached</b></li>
<li><b>Protected</b></li>
<li><b>ExistingSysMem</b></li>
<li><b>ExistingKernelSysMem</b></li>
</ul>
</li>
</ul>
The D3DDDI_ID_NOTAPPLICABLE constant is defined in D3dukmdt.h.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dumddi.h, D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/5b74c989-1a62-4415-a19a-dd0ba2fcff83">CreateResource</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544137">D3DDDICB_ALLOCATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544651">D3DDDI_SURFACEINFO</a>



<a href="https://msdn.microsoft.com/edf59add-0155-4619-9c7c-fdb63b954f85">D3DKMDDI_SHAREDPRIMARYSURFACEDATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557559">DXGKARG_CREATEALLOCATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff560960">DXGK_ALLOCATIONINFO</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/a61e6c6a-3992-429c-ad8c-5f1a61dc7b8b">pfnAllocateCb</a>