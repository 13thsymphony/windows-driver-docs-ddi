---
UID: NS:d3d10umddi._D3D11_1DDI_GETCAPTUREHANDLEDATA
title: "_D3D11_1DDI_GETCAPTUREHANDLEDATA"
author: windows-driver-content
description: Defines a resource allocation in a call to the GetCaptureHandle function.
old-location: display\d3d11_1ddi_getcapturehandledata.htm
old-project: display
ms.assetid: f12ace3a-2bb4-433b-b987-2027a48f4c14
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA structure [Display Devices], _D3D11_1DDI_GETCAPTUREHANDLEDATA, d3d10umddi/D3D11_1DDI_GETCAPTUREHANDLEDATA, display.d3d11_1ddi_getcapturehandledata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	D3D11_1DDI_GETCAPTUREHANDLEDATA
product: Windows
targetos: Windows
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# _D3D11_1DDI_GETCAPTUREHANDLEDATA structure
Defines a resource allocation in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetCaptureHandle</a> function.

## Syntax
````
typedef struct _D3D11_1DDI_GETCAPTUREHANDLEDATA {
  D3D10DDI_HRESOURCE hResource;
  UINT               ArrayIndex;
  D3DKMT_HANDLE      hAllocation;
  UINT               DataOffset;
  UINT               DataSize;
} D3D11_1DDI_GETCAPTUREHANDLEDATA;
````

## Members


`hResource`

[in] The handle to the resource for which the allocation handle is to be obtained.

The Direct3D version 11 and later runtime will have already verified that this resource was created using the <b>D3D11_DDI_BIND_CAPTURE</b> value in the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a> enumeration.

`ArrayIndex`

[in] The array element from which the data is to be obtained.

If the resource was not created as a texture array, this value is zero. For a texture array, the Direct3D version 11 and later runtime will have already verified that the array is valid.

`hAllocation`

[out] The driver-provided address of the kernel mode allocation handle associated with this allocation.

`DataOffset`

[out] The driver-provided offset of the requested data within the allocation.

If the resource was not created as a texture array, this value is typically zero.  For a texture array, this value is the offset of the array element data within the allocation.

`DataSize`

[out] The driver-provided size of the requested data within the allocation.

If the resource was not created as a texture array, this value is typically the size of the allocation, in bytes.  For a texture array, this value is the size of the element data within the allocation.

## Remarks
When the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetCaptureHandle</a> function is called, the driver updates the structure with the kernel mode allocation handle associated with the specified resource, as well as the size of the resource data and its offset within an allocated block of memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getcapturehandle.md">GetCaptureHandle</a>



<a href="..\d3d10umddi\ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md">D3D10_DDI_RESOURCE_BIND_FLAG</a>