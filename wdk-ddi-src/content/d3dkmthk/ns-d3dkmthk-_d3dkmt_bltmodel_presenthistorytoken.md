---
UID: NS:d3dkmthk._D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN
title: "_D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN"
author: windows-driver-content
description: The D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure identifies a bit-block transfer (bitblt) present-history operation.
old-location: display\d3dkmt_bltmodel_presenthistorytoken.htm
old-project: display
ms.assetid: 841c1e6f-4561-4c37-a509-d9c0e9054022
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN, D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure [Display Devices], OpenGL_Structs_45310e71-a7c5-42c6-be41-e48e30203c42.xml, _D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN, d3dkmthk/D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN, display.d3dkmt_bltmodel_presenthistorytoken
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
req.target-min-winverclnt: D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system.
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
-	D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN
product: Windows
targetos: Windows
req.typenames: D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN
---

# _D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure
The D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure identifies a bit-block transfer (bitblt) present-history operation.

## Syntax
````
typedef struct _D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN {
  ULONG64             hLogicalSurface;
  ULONG64             hPhysicalSurface;
  ULONG64             EventId;
  D3DKMT_DIRTYREGIONS DirtyRegions;
} D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN;
````

## Members


`DirtyRegions`

[in] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dirtyregions.md">D3DKMT_DIRTYREGIONS</a> structure that identifies the active rectangles (dirty regions) of the bitblt surface.

`EventId`

[in] A 64-bit value that identifies the bitblt event.

`hLogicalSurface`

[in] A 64-bit value that specifies the handle to a logical surface to copy from.

`hPhysicalSurface`

[in] A 64-bit value that specifies the handle to a physical surface to copy to.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system. D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN is supported beginning with the Windows 7 operating system. |
| **Header** | d3dkmthk.h (include D3dkmthk.h) |

## See Also

<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_dirtyregions.md">D3DKMT_DIRTYREGIONS</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_presenthistorytoken.md">D3DKMT_PRESENTHISTORYTOKEN</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_BLTMODEL_PRESENTHISTORYTOKEN structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>