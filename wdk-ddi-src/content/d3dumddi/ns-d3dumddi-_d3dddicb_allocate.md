---
UID: NS:d3dumddi._D3DDDICB_ALLOCATE
title: "_D3DDDICB_ALLOCATE"
author: windows-driver-content
description: The D3DDDICB_ALLOCATE structure contains information for allocating memory.
old-location: display\d3dddicb_allocate.htm
old-project: display
ms.assetid: 76ebc960-ff63-40eb-842b-acdb549ecdaa
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDICB_ALLOCATE, D3DDDICB_ALLOCATE structure [Display Devices], D3D_param_Structs_6fe53e00-df9e-4e4b-b5e8-2cb3a1571868.xml, _D3DDDICB_ALLOCATE, d3dumddi/D3DDDICB_ALLOCATE, display.d3dddicb_allocate
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
-	D3DDDICB_ALLOCATE
product: Windows
targetos: Windows
req.typenames: D3DDDICB_ALLOCATE
---

# _D3DDDICB_ALLOCATE structure
The D3DDDICB_ALLOCATE structure contains information for allocating memory.

## Syntax
````
typedef struct _D3DDDICB_ALLOCATE {
  const VOID            *pPrivateDriverData;
  UINT                  PrivateDriverDataSize;
  HANDLE                hResource;
  D3DKMT_HANDLE         hKMResource;
  UINT                  NumAllocations;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7)
  union {
    D3DDDI_ALLOCATIONINFO  *pAllocationInfo;
    D3DDDI_ALLOCATIONINFO2 *pAllocationInfo2;
  };
#else 
  D3DDDI_ALLOCATIONINFO *pAllocationInfo;
} D3DDDICB_ALLOCATE;
````

## Members


`pPrivateDriverData`

[in] A pointer to private data, which is passed to the display miniport driver. This data is per resource and not per allocation. If allocations are attached to an existing resource, the current data should overwrite the former data.

`PrivateDriverDataSize`

[in] The size, in bytes, of the private data that is pointed to by <b>pPrivateDriverData</b>.

`hResource`

[in] A handle to the resource that is associated with the allocations. 

When the user-mode display driver calls the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a> function, the driver should assign the value that was received from the <b>hResource</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure in a call to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>, or the <b>hRTResource</b> parameter in a call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a>. It should assign the value to associate the allocations with the resource, or assign <b>NULL</b> to associate the allocations with the device. The driver must assign a non-<b>NULL</b> value for allocations that are created in response to shared resources. Shared resources might result from <b>CreateResource</b> calls with the <b>SharedResource</b> bit-field flag set in the <b>Flags</b> member of D3DDDIARG_CREATERESOURCE. They might also result from <b>CreateResource(D3D10)</b> or <b>CreateResource(D3D11)</b> calls, with the D3D10_DDI_RESOURCE_MISC_SHARED value set in the <b>MiscFlags</b> member of either <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a> or <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createresource.md">D3D11DDIARG_CREATERESOURCE</a>.

The Microsoft Direct3D runtime should use this handle in driver calls to identify the resource.

`hKMResource`

[out] A D3DKMT_HANDLE data type that represents a kernel-mode handle to the resource that is associated with the allocations.

The Direct3D runtime creates and returns a kernel-mode resource handle only if the user-mode display driver sets the <b>hResource</b> member of D3DDDICB_ALLOCATE to the user-mode runtime resource handle that was received from the <b>hResource</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure. This handle is received in a call to <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>, or from the <i>hResource</i> parameter in a call to either <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a> or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a>. 

The Direct3D runtime generates a unique handle and passes it back to the user-mode display driver. The user-mode display driver can insert the kernel-mode resource handle in the command stream for subsequent use by the display miniport driver.

`NumAllocations`

[in] The number of elements in the array at <b>pAllocationInfo</b>, which represents the number of allocations to allocate.

`pAllocationInfo`

[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structures that describe the allocations to allocate.

[in] An array of <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structures that describe the allocations to allocate.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createresource.md">D3D11DDIARG_CREATERESOURCE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createresource.md">CreateResource(D3D10)</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_allocatecb.md">pfnAllocateCb</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createresource.md">CreateResource(D3D11)</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createresource.md">D3D10DDIARG_CREATERESOURCE</a>