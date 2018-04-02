---
UID: NS:d3dkmthk._D3DKMT_RECLAIMALLOCATIONS2
title: "_D3DKMT_RECLAIMALLOCATIONS2"
author: windows-driver-content
description: D3DKMT_RECLAIMALLOCATIONS2 describes video memory resources that are to be reclaimed and that the driver previously offered for reuse. Used with the D3DKMTReclaimAllocations2 function.
old-location: display\d3dkmt_reclaimallocations2.htm
old-project: display
ms.assetid: 7980F1FD-D7C2-4C74-8652-89FD38BE4D1F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMT_RECLAIMALLOCATIONS2, D3DKMT_RECLAIMALLOCATIONS2 structure [Display Devices], _D3DKMT_RECLAIMALLOCATIONS2, d3dkmthk/D3DKMT_RECLAIMALLOCATIONS2, display.d3dkmt_reclaimallocations2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	D3dkmthk.h
api_name:
-	D3DKMT_RECLAIMALLOCATIONS2
product:
- Windows
targetos: Windows
req.typenames: D3DKMT_RECLAIMALLOCATIONS2
---

# _D3DKMT_RECLAIMALLOCATIONS2 structure
<b>D3DKMT_RECLAIMALLOCATIONS2</b> describes video memory resources that are to be reclaimed and that the driver  previously offered  for reuse. Used with the  <a href="https://msdn.microsoft.com/library/windows/hardware/dn906780">D3DKMTReclaimAllocations2</a> function.

## Syntax
```
typedef struct _D3DKMT_RECLAIMALLOCATIONS2 {
  D3DKMT_HANDLE       hPagingQueue;
  UINT                NumAllocations;
  D3DKMT_HANDLE       *pResources;
  CONST D3DKMT_HANDLE *HandleList;
  union {
    BOOL                  *pDiscarded;
    D3DDDI_RECLAIM_RESULT *pResults;
  };
  BOOL                *pDiscarded;
  UINT64              PagingFenceValue;
} D3DKMT_RECLAIMALLOCATIONS2;
```

## Members


`hPagingQueue`

[in] A handle to the device that created the allocations.

`NumAllocations`

[in] The number of items in the <b>pResources</b>, <b>HandleList</b>, or  <b>pDiscarded</b> members, whichever is not <b>NULL</b>.

`pResources`

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent Direct3D runtime resource handles.

`HandleList`

[in] An array of <b>D3DKMT_HANDLE</b> data types that represent kernel-mode handles to the allocations that are to be reclaimed.

If <b>HandleList</b> is not <b>NULL</b>, the <b>pResources</b> member must be <b>NULL</b>.

`pDiscarded`

[out] Optional array of boolean variables  specifying whether each resource or allocation was discarded.

`PagingFenceValue`

The paging fence to synchronize against before submitting work to the GPU which references any of the resources or allocations in the provided arrays.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |