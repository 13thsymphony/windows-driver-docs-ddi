---
UID: NS:d3dumddi._D3DDDI_OVERLAYINFO
title: "_D3DDDI_OVERLAYINFO"
author: windows-driver-content
description: The D3DDDI_OVERLAYINFO structure describes information about an overlay.
old-location: display\d3dddi_overlayinfo.htm
old-project: display
ms.assetid: e2732ea9-4fd6-416d-8fb0-1ccf1d1ad0df
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDI_OVERLAYINFO, D3DDDI_OVERLAYINFO structure [Display Devices], D3D_other_Structs_b9046736-50b8-46b1-92c9-5d879ee7c64d.xml, _D3DDDI_OVERLAYINFO, d3dumddi/D3DDDI_OVERLAYINFO, display.d3dddi_overlayinfo
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
-	D3DDDI_OVERLAYINFO
product: Windows
targetos: Windows
req.typenames: D3DDDI_OVERLAYINFO
---

# _D3DDDI_OVERLAYINFO structure
The D3DDDI_OVERLAYINFO structure describes information about an overlay.

## Syntax
````
typedef struct _D3DDDI_OVERLAYINFO {
  HANDLE                  hResource;
  UINT                    SubResourceIndex;
  RECT                    DstRect;
  RECT                    SrcRect;
  UINT                    DstColorKeyLow;
  UINT                    DstColorKeyHigh;
  UINT                    SrcColorKeyLow;
  UINT                    SrcColorKeyHigh;
  D3DDDI_OVERLAYINFOFLAGS Flags;
} D3DDDI_OVERLAYINFO;
````

## Members


`hResource`

[in] A handle to the resource that is displayed by using the overlay. The resource is created through a call to the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a> function with the <b>Overlay</b> bit-field flag set in the <b>Flags</b> member of the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a> structure that is pointed to by the <i>pResource</i> parameter.

`SubResourceIndex`

[in] The index to the subresource if the resource that is specified by the <b>hResource</b> member contains a list of allocations.

`DstRect`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure for the destination rectangle, which contains the output coordinates for the display.

`SrcRect`

[in] A RECT structure for the source rectangle that is displayed.

`DstColorKeyLow`

[in] A value for the destination color key when the <b>DstColorKey</b> bit-field flag is set in the <b>Flags</b> member. If the color key is a range, <b>DstColorKeyLow</b> contains the low end of the range. The value is in the native format of the primary surface that is overlayed.

`DstColorKeyHigh`

[in] The high end of the destination color key range when the <b>DstColorKeyRange</b> bit-field flag is set in <b>Flags</b>. The value is in the native format of the primary surface that is overlayed.

`SrcColorKeyLow`

[in] A value for the source color key when the <b>SrcColorKey</b> bit-field flag is set in the <b>Flags</b> member. If the color key is a range, <b>SrcColorKeyLow</b> contains the low end of the range. The value is in the native format of the overlay resource that is displayed.

`SrcColorKeyHigh`

[in] The high end of the source color key range when the <b>SrcColorKeyRange</b> bit-field flag is set in <b>Flags</b>. The value is in the native format of the overlay resource that is displayed.

`Flags`

[in] A <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlayinfoflags.md">D3DDDI_OVERLAYINFOFLAGS</a> structure that identifies the type of overlay operation to perform. Note that some flags are mutually exclusive with other flags. For more information, see the following Remarks section.

## Remarks
The <b>SrcColorKey</b>, <b>SrcColorKeyRange</b>, <b>DstColorKey</b>, and <b>DstColorKeyRange</b> bit-field flags are never set simultaneously in the <b>Flags</b> member.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlayinfoflags.md">D3DDDI_OVERLAYINFOFLAGS</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddiarg_createresource.md">D3DDDIARG_CREATERESOURCE</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlay.md">UpdateOverlay</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createresource.md">CreateResource</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createoverlay.md">CreateOverlay</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>