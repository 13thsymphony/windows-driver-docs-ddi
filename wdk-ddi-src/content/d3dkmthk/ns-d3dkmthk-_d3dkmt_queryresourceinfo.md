---
UID: NS:d3dkmthk._D3DKMT_QUERYRESOURCEINFO
title: "_D3DKMT_QUERYRESOURCEINFO"
author: windows-driver-content
description: The D3DKMT_QUERYRESOURCEINFO structure describes parameters for retrieving information about a resource.
old-location: display\d3dkmt_queryresourceinfo.htm
old-project: display
ms.assetid: 14078b2b-8951-48df-912a-e053bc997dde
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMT_QUERYRESOURCEINFO, D3DKMT_QUERYRESOURCEINFO structure [Display Devices], OpenGL_Structs_1bab95d7-d3a4-4380-939f-bca4e2d98478.xml, _D3DKMT_QUERYRESOURCEINFO, d3dkmthk/D3DKMT_QUERYRESOURCEINFO, display.d3dkmt_queryresourceinfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
-	d3dkmthk.h
api_name:
-	D3DKMT_QUERYRESOURCEINFO
product: Windows
targetos: Windows
req.typenames: D3DKMT_QUERYRESOURCEINFO
---

# _D3DKMT_QUERYRESOURCEINFO structure
The D3DKMT_QUERYRESOURCEINFO structure describes parameters for retrieving information about a resource.

## Syntax
````
typedef struct _D3DKMT_QUERYRESOURCEINFO {
  D3DKMT_HANDLE hDevice;
  D3DKMT_HANDLE hGlobalShare;
  VOID          *pPrivateRuntimeData;
  UINT          PrivateRuntimeDataSize;
  UINT          TotalPrivateDriverDataSize;
  UINT          ResourcePrivateDriverDataSize;
  UINT          NumAllocations;
} D3DKMT_QUERYRESOURCEINFO;
````

## Members


`hDevice`

[in] A handle to the device that the resource and allocations are associated with.

`hGlobalShare`

[in] A handle to the shared resource to open.

`pPrivateRuntimeData`

[in] If non-<b>NULL</b>, a pointer to a buffer that receives the runtime-private data that is supplied at create time. The OpenGL ICD should first call the <a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryresourceinfo.md">D3DKMTQueryResourceInfo</a> function with <b>pPrivateRuntimeData</b> set to <b>NULL</b> to obtain the buffer size and then call again with the correct size buffer.

`PrivateRuntimeDataSize`

[in/out] The size, in bytes, of the buffer that <b>pPrivateRuntimeData</b> points to. If <b>pPrivateRuntimeData</b> is <b>NULL</b>, <b>PrivateRuntimeDataSize</b> is set to the size, in bytes, that is required for the buffer to store the runtime-private data.

`TotalPrivateDriverDataSize`

[out] The size, in bytes, of the buffer that is required to hold the private driver data for all of the allocations that are associated with the resource.

`ResourcePrivateDriverDataSize`

[out] The size, in bytes, of the buffer that is required to hold the private driver data for the resource.

`NumAllocations`

[out] The number of allocations that are associated with the resource.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtopenresource.md">D3DKMTOpenResource</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtqueryresourceinfo.md">D3DKMTQueryResourceInfo</a>