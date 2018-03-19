---
UID: NS:dxgiddi.DXGI_DDI_ARG_BLT1
title: DXGI_DDI_ARG_BLT1
author: windows-driver-content
description: Describes the parameters of a bit-block transfer (bitblt) that include specifications for a source rectangle. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.
old-location: display\dxgi_ddi_arg_blt1.htm
old-project: display
ms.assetid: bc7c2693-6a18-4335-8921-363981a830f1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGI_DDI_ARG_BLT1, DXGI_DDI_ARG_BLT1 structure [Display Devices], display.dxgi_ddi_arg_blt1, dxgiddi/DXGI_DDI_ARG_BLT1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8,WDDM 1.2 and later
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
-	Dxgiddi.h
api_name:
-	DXGI_DDI_ARG_BLT1
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_ARG_BLT1
---

# DXGI_DDI_ARG_BLT1 structure
Describes the parameters of a bit-block transfer (bitblt) that include specifications for a  source rectangle. Used by Windows Display Driver Model (WDDM) 1.2 and later user-mode display drivers.

## Syntax
````
typedef struct DXGI_DDI_ARG_BLT1 {
  DXGI_DDI_HDEVICE       hDevice;
  DXGI_DDI_HRESOURCE     hDstResource;
  UINT                   DstSubresource;
  UINT                   DstLeft;
  UINT                   DstTop;
  UINT                   DstRight;
  UINT                   DstBottom;
  DXGI_DDI_HRESOURCE     hSrcResource;
  UINT                   SrcSubresource;
  UINT                   SrcLeft;
  UINT                   SrcTop;
  UINT                   SrcRight;
  UINT                   SrcBottom;
  DXGI_DDI_ARG_BLT_FLAGS Flags;
  DXGI_DDI_MODE_ROTATION Rotate;
} DXGI_DDI_ARG_BLT1;
````

## Members


`hDevice`

[in] A handle to the display device (graphics context) on which the driver performs the bitblt. The Direct3D runtime passes this handle to the driver in the <b>hDrvDevice</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a> structure when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the display device.

`hDstResource`

[in] A handle to the destination resource.

`DstSubresource`

[in] The index to the destination surface within the resource.

`DstLeft`

[in] The <i>x</i>-coordinate of the upper-left corner of the destination rectangle.

`DstTop`

[in] The <i>y</i>-coordinate of the upper-left corner of the destination rectangle.

`DstRight`

[in] The <i>x</i>-coordinate of the lower-right corner of the destination rectangle.

`DstBottom`

[in] The <i>y</i>-coordinate of the lower-right corner of the destination rectangle.

`hSrcResource`

[in] A handle to the source resource.

`SrcSubresource`

[in] The index to the source surface within the resource.

`SrcLeft`

[in] The <i>x</i>-coordinate of the upper-left corner of the source rectangle.

`SrcTop`

[in] The <i>y</i>-coordinate of the upper-left corner of the source rectangle.

`SrcRight`

[in] The <i>x</i>-coordinate of the lower-right corner of the source rectangle.

`SrcBottom`

[in] The <i>y</i>-coordinate of the lower-right corner of the destination rectangle.

`Flags`

[in] A <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_blt_flags.md">DXGI_DDI_ARG_BLT_FLAGS</a> structure that identifies the type of bitblt to perform.

`Rotate`

[in] A value of type <a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_rotation.md">DXGI_DDI_MODE_ROTATION</a> that identifies the orientation of the display mode.

## Remarks
The source rectangle specified by the members <b>SrcLeft</b>, <b>SrcTop</b>, <b>SrcRight</b>, and <b>SrcBottom</b> is typically a dirty subrectangle.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8,WDDM 1.2 and later Windows 8,WDDM 1.2 and later |
| **Header** | dxgiddi.h (include D3d10umddi.h) |

## See Also

<a href="..\dxgiddi\ne-dxgiddi-dxgi_ddi_mode_rotation.md">DXGI_DDI_MODE_ROTATION</a>



<a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_arg_blt_flags.md">DXGI_DDI_ARG_BLT_FLAGS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdevice.md">D3D10DDIARG_CREATEDEVICE</a>