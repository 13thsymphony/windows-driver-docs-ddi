---
UID: NS:d3dumddi._D3DDDIARG_DEPTHFILL
title: "_D3DDDIARG_DEPTHFILL"
author: windows-driver-content
description: The D3DDDIARG_DEPTHFILL structure describes the parameters of a depth-fill operation.
old-location: display\d3dddiarg_depthfill.htm
old-project: display
ms.assetid: e4070d53-bdd6-4708-857d-7ed1e9699e21
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DDDIARG_DEPTHFILL, D3DDDIARG_DEPTHFILL structure [Display Devices], UMDisplayDriver_param_Structs_94ba7961-5956-4939-830f-eaa15aeca614.xml, _D3DDDIARG_DEPTHFILL, d3dumddi/D3DDDIARG_DEPTHFILL, display.d3dddiarg_depthfill
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
-	D3DDDIARG_DEPTHFILL
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DEPTHFILL
---

# _D3DDDIARG_DEPTHFILL structure
The D3DDDIARG_DEPTHFILL structure describes the parameters of a depth-fill operation.

## Syntax
````
typedef struct _D3DDDIARG_DEPTHFILL {
  HANDLE hResource;
  UINT   SubResourceIndex;
  RECT   DstRect;
  UINT   Depth;
} D3DDDIARG_DEPTHFILL;
````

## Members


`Depth`

A pixel value that is specified in native format for the fill depth.

`DstRect`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a> structure that indicates the upper-left and lower-right points of a rectangle on the buffer to depth fill.

`hResource`

[in] A handle to the resource.

`SubResourceIndex`

[in] The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or buffer, on which a rectangular area is depth-filled.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_depthfill.md">DepthFill</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569236">RECTL</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_DEPTHFILL structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>