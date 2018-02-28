---
UID: NS:d3d12umddi.D3D12DDI_ALLOCATION_INFO_0022
title: D3D12DDI_ALLOCATION_INFO_0022
author: windows-driver-content
description: Specifies allocation information.
old-location: display\d3d12ddi_allocation_info_0022.htm
old-project: display
ms.assetid: A600C402-EB77-4C44-8349-96DAF11B807C
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_ALLOCATION_INFO_0022, D3D12DDI_ALLOCATION_INFO_0022 structure [Display Devices], d3d12umddi/D3D12DDI_ALLOCATION_INFO_0022, display.d3d12ddi_allocation_info_0022
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	D3d12umddi.h
api_name:
-	D3D12DDI_ALLOCATION_INFO_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_ALLOCATION_INFO_0022
---

# D3D12DDI_ALLOCATION_INFO_0022 structure
Specifies allocation information.

## Syntax
````
typedef struct D3D12DDI_ALLOCATION_INFO_0022 {
  D3DKMT_HANDLE                       hAllocation;
  const VOID                          *pSystemMem;
  VOID                                *pPrivateDriverData;
  UINT                                PrivateDriverDataSize;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID      VidPnSourceId;
  D3D12DDI_ALLOCATION_INFO_FLAGS_0022 Flags;
  D3DGPU_VIRTUAL_ADDRESS              GpuVirtualAddress;
  UINT                                Priority;
  ULONG_PTR                           Reserved[5];
} D3D12DDI_ALLOCATION_INFO_0022;
````

## Members


`Flags`

Flags that identify the type of the allocation information as a <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_allocation_info_flags_0022.md">D3D12DDI_ALLOCATION_INFO_FLAGS_0022</a> value.

`GpuVirtualAddress`

A virtual address in the GPU.

`hAllocation`

The handle of an allocation.

`pPrivateDriverData`

Pointer to a buffer that contains optional private driver data.

`Priority`

A priority for the allocation.

`PrivateDriverDataSize`

Size of the private driver data buffer.

`pSystemMem`

Pointer to a system memory location that is preallocated. If the allocation uses video memory, specify null.

`Reserved`

Reserved.

`VidPnSourceId`

A zero-based ID of the video present source in a path of a video present network topology.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_allocation_info_flags_0022.md">D3D12DDI_ALLOCATION_INFO_FLAGS_0022</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_ALLOCATION_INFO_0022 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>