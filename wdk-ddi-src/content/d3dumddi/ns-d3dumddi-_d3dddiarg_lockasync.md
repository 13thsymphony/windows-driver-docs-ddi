---
UID: NS:d3dumddi._D3DDDIARG_LOCKASYNC
title: "_D3DDDIARG_LOCKASYNC"
author: windows-driver-content
description: The D3DDDIARG_LOCKASYNC structure describes a resource or a surface within the resource to lock.
old-location: display\d3dddiarg_lockasync.htm
old-project: display
ms.assetid: dfe2ab95-e494-430d-81c7-8f209a37024f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_LOCKASYNC, D3DDDIARG_LOCKASYNC structure [Display Devices], UMDisplayDriver_param_Structs_24593944-e4ac-4650-82d5-c5fc26a6a770.xml, _D3DDDIARG_LOCKASYNC, d3dumddi/D3DDDIARG_LOCKASYNC, display.d3dddiarg_lockasync
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
-	D3DDDIARG_LOCKASYNC
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_LOCKASYNC
---

# _D3DDDIARG_LOCKASYNC structure
The D3DDDIARG_LOCKASYNC structure describes a resource or a surface within the resource to lock.

## Syntax
````
typedef struct _D3DDDIARG_LOCKASYNC {
  HANDLE                 hResource;
  UINT                   SubResourceIndex;
  D3DDDI_LOCKASYNCFLAGS  Flags;
  union {
    D3DDDIRANGE Range;
    RECT        Area;
    D3DDDIBOX   Box;
  };
  HANDLE                 hCookie;
  VOID                   *pSurfData;
  UINT                   Pitch;
  UINT                   SlicePitch;
#if (D3D_UMD_INTERFACE_VERSION >= D3D_UMD_INTERFACE_VERSION_WIN7)
  D3DGPU_VIRTUAL_ADDRESS GpuVirtualAddress;
#endif 
} D3DDDIARG_LOCKASYNC;
````

## Members


`hResource`

[in] A handle to the resource to be locked.

`SubResourceIndex`

[in] The zero-based index into the resource that <b>hResource</b> specifies. This index indicates the subresource or surface to be locked.

`Flags`

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_lockasyncflags.md">D3DDDI_LOCKASYNCFLAGS</a> structure that indicates, in bit-field flags, how to lock the resource. 

<div class="alert"><b>Note</b>    Some flags are mutually exclusive with other flags. For more information, see the following Remarks section.</div>
<div> </div>

`hCookie`

[out] A handle that represents the renamed resource. This handle is valid only if the <b>Discard</b> bit-field flag is set in the D3DDDI_LOCKASYNCFLAGS structure that <b>Flags</b> specifies.

`pSurfData`

[out] A pointer to the memory region for the resource that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function returns this pointer to the Microsoft Direct3D runtime.

`Pitch`

[out] The pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function returns this pitch value to the Direct3D runtime.

`SlicePitch`

[out] The slice pitch, in bytes, of the surface that was locked. The user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a> function returns this slice pitch value to the Direct3D runtime.

`GpuVirtualAddress`

This member is reserved and should be set to zero.

This member is available beginning with Windows 7.

## Remarks
The members of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_lockasyncflags.md">D3DDDI_LOCKASYNCFLAGS</a> structure that the <b>Flags</b> member specifies must adhere to the following rules:

<ul>
<li>
The <b>NoOverwrite</b> bit-field flag must not be simultaneously set with the <b>Discard</b> bit-field flag.

</li>
<li>
Only one of the <b>RangeValid</b>, <b>AreaValid</b>, and <b>BoxValid</b> bit-field flags must be set at any time.

</li>
</ul>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_lockasyncflags.md">D3DDDI_LOCKASYNCFLAGS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_lockasync.md">LockAsync</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>