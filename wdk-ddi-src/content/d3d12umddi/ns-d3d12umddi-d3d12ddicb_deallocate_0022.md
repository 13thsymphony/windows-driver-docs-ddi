---
UID: NS:d3d12umddi.D3D12DDICB_DEALLOCATE_0022
title: D3D12DDICB_DEALLOCATE_0022
author: windows-driver-content
description: Specifies values for use with a deallocation callback function.
old-location: display\d3d12ddicb_deallocate_0022.htm
old-project: display
ms.assetid: 977868D1-02E1-4460-9194-2079B986045E
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDICB_DEALLOCATE_0022, D3D12DDICB_DEALLOCATE_0022 structure [Display Devices], d3d12umddi/D3D12DDICB_DEALLOCATE_0022, display.d3d12ddicb_deallocate_0022
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
-	D3D12DDICB_DEALLOCATE_0022
product:
- Windows
targetos: Windows
req.typenames: D3D12DDICB_DEALLOCATE_0022
---

# D3D12DDICB_DEALLOCATE_0022 structure
Specifies values for use with a deallocation callback function.

## Syntax
```
typedef struct D3D12DDICB_DEALLOCATE_0022 {
  HANDLE                         hResource;
  UINT                           NumAllocations;
  CONST D3DKMT_HANDLE            *HandleList;
  D3D12DDI_DEALLOCATE_FLAGS_0022 Flags;
};
```

## Members


`hResource`

The handle of a resource.

`NumAllocations`



`HandleList`

A pointer to a list of kernel handles.

`Flags`

Flags to use for deallocation, as specified in the <a href="https://msdn.microsoft.com/17E3C01A-0716-4B3C-B4B3-72B055FB40EA">D3D12DDI_DEALLOCATE_FLAGS_0022</a> enumeration.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/17E3C01A-0716-4B3C-B4B3-72B055FB40EA">D3D12DDI_DEALLOCATE_FLAGS_0022</a>