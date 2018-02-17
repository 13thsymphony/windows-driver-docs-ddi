---
UID: NE:d3d10umddi.D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG
title: D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG
author: windows-driver-content
description: The D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG enumeration type contains values that identify the type of depth-stencil view to create through a call to the driver's CreateDepthStencilView(D3D11) function.
old-location: display\d3d11_ddi_createdepthstencilview_flag.htm
old-project: display
ms.assetid: 197ba249-f7a4-4c98-914c-ecb8984ffd5d
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_DDI_CREATE_DSV_READ_ONLY_DEPTH, UMDisplayDriver_Dx11param_Structs_1148b880-7553-4a83-b602-c6b80d79b29f.xml, d3d10umddi/D3D11_DDI_CREATE_DSV_READ_ONLY_DEPTH, D3D11_DDI_CREATE_DSV_READ_ONLY_STENCIL, d3d10umddi/D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG, d3d10umddi/D3D11_DDI_CREATE_DSV_READ_ONLY_STENCIL, D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG enumeration [Display Devices], d3d10umddi/D3D11_DDI_CREATE_DSV_FLAG_MASK, display.d3d11_ddi_createdepthstencilview_flag, D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG, D3D11_DDI_CREATE_DSV_FLAG_MASK
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3d10umddi.h
apiname:
-	D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG
product: Windows
targetos: Windows
req.typenames: D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG
---

# D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG Enumeration
The D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG enumeration type contains values that identify the type of depth-stencil view to create through a call to the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdepthstencilview.md">CreateDepthStencilView(D3D11)</a> function.

## Syntax
````
typedef enum D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG { 
  D3D11_DDI_CREATE_DSV_READ_ONLY_DEPTH    = 0x01L,
  D3D11_DDI_CREATE_DSV_READ_ONLY_STENCIL  = 0x02L,
  D3D11_DDI_CREATE_DSV_FLAG_MASK          = 0x03L
} D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG;
````

## Constants

<table>
            
                <tr>
                    <td>D3D11_DDI_CREATE_DSV_FLAG_MASK</td>
                    <td>A mask value that indicates the valid bitfields in a bitwise OR combination of the values from this enumeration.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_CREATE_DSV_READ_ONLY_DEPTH</td>
                    <td>The driver should create a read-only depth view.</td>
                </tr>
            
                <tr>
                    <td>D3D11_DDI_CREATE_DSV_READ_ONLY_STENCIL</td>
                    <td>The driver should create a read-only stencil view.</td>
                </tr>
</table>

    ## Remarks

        D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG values are specified in the <b>Flags</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createdepthstencilview.md">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a> structure to indicate the type of depth-stencil view to create.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG is supported beginning with the Windows 7 operating system. D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG is supported beginning with the Windows 7 operating system. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_createdepthstencilview.md">D3D11DDIARG_CREATEDEPTHSTENCILVIEW</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11ddi_createdepthstencilview.md">CreateDepthStencilView(D3D11)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_DDI_CREATEDEPTHSTENCILVIEW_FLAG enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>