---
UID: NE:d3d10umddi.D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG
title: D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG
author: windows-driver-content
description: The D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG enumeration type contains values that identify the type of depth-stencil view to create through a call to the driver's CreateDepthStencilView(D3D11) function.
old-location: display\d3d11_ddi_createdepthstencilview_flag.htm
old-project: display
ms.assetid: 197ba249-f7a4-4c98-914c-ecb8984ffd5d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG, D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG enumeration [Display Devices], D3D11_DDI_CREATE_DSV_FLAG_MASK, D3D11_DDI_CREATE_DSV_READ_ONLY_DEPTH, D3D11_DDI_CREATE_DSV_READ_ONLY_STENCIL, UMDisplayDriver_Dx11param_Structs_1148b880-7553-4a83-b602-c6b80d79b29f.xml, d3d10umddi/D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG, d3d10umddi/D3D11_DDI_CREATE_DSV_FLAG_MASK, d3d10umddi/D3D11_DDI_CREATE_DSV_READ_ONLY_DEPTH, d3d10umddi/D3D11_DDI_CREATE_DSV_READ_ONLY_STENCIL, display.d3d11_ddi_createdepthstencilview_flag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
api_name:
-	D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG
product:
- Windows
targetos: Windows
req.typenames: D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG
---

# D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG Enumeration
The D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG enumeration type contains values that identify the type of depth-stencil view to create through a call to the driver's <a href="https://msdn.microsoft.com/cf4c34da-71df-4b49-b1c8-73d1a2dbc3cb">CreateDepthStencilView(D3D11)</a> function.

## Syntax
```
typedef enum D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG {
  D3D11_DDI_CREATE_DSV_READ_ONLY_DEPTH    ,
  D3D11_DDI_CREATE_DSV_READ_ONLY_STENCIL  ,
  D3D11_DDI_CREATE_DSV_FLAG_MASK
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3D11_DDI_CREATE_DSV_READ_ONLY_DEPTH</td>
                    <td>The driver should create a read-only depth view.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_CREATE_DSV_READ_ONLY_STENCIL</td>
                    <td>The driver should create a read-only stencil view.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_CREATE_DSV_FLAG_MASK</td>
                    <td>A mask value that indicates the valid bitfields in a bitwise OR combination of the values from this enumeration.</td>
                </tr>
</table>

## Remarks

D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG values are specified in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542048">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a> structure to indicate the type of depth-stencil view to create.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG is supported beginning with the Windows 7 operating system. D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/cf4c34da-71df-4b49-b1c8-73d1a2dbc3cb">CreateDepthStencilView(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542048">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a>