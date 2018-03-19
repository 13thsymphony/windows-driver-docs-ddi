---
UID: NS:d3dumddi.D3DDDIARG_UPDATESUBRESOURCEUP
title: D3DDDIARG_UPDATESUBRESOURCEUP
author: windows-driver-content
description: Describes info that's used to update a destination subresource region from a source system-memory region. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.
old-location: display\d3dddiarg_updatesubresourceup.htm
old-project: display
ms.assetid: 27BE493F-8F70-4FBF-AA58-D6ACB27BFC2D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_UPDATESUBRESOURCEUP, D3DDDIARG_UPDATESUBRESOURCEUP structure [Display Devices], d3dumddi/D3DDDIARG_UPDATESUBRESOURCEUP, display.d3dddiarg_updatesubresourceup
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
api_name:
-	D3DDDIARG_UPDATESUBRESOURCEUP
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_UPDATESUBRESOURCEUP
---

# D3DDDIARG_UPDATESUBRESOURCEUP structure
Describes info that's used to update a destination subresource region from a source system-memory region. Used by Windows Display Driver Model (WDDM) 1.3 and later user-mode display drivers.

## Syntax
````
typedef struct D3DDDIARG_UPDATESUBRESOURCEUP {
  HANDLE              hResource;
  UINT                SubResourceIndex;
  D3DDDIBOX           DstBox;
  const VOID          *pSysMemUP;
  UINT                RowPitch;
  UINT                DepthPitch;
  D3DDDIARG_COPYFLAGS Flags;
} D3DDDIARG_UPDATESUBRESOURCEUP;
````

## Members


`hResource`

A handle to the destination resource to copy to.

`SubResourceIndex`

The index of the destination subresource to which data is to be copied.

`DstBox`

A destination region, of type  <a href="..\d3dumddi\ns-d3dumddi-_d3dddibox.md">D3DDDIBOX</a>, of the subresource to which data is to be copied. If <b>Flags</b>-&gt;<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_copyflags.md">BoxValid</a> is not set, the entire subresource must be updated.

`pSysMemUP`

A pointer to the beginning address of the source data that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updatesubresourceup.md">pfnUpdateSubresourceUP</a> function copies to update the destination subresouce.

`RowPitch`

The offset, in bytes, to move to the next row of source data.

`DepthPitch`

The offset, in bytes, to move to the next depth slice of source data.

`Flags`

A <a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_copyflags.md">D3DDDIARG_COPYFLAGS</a> structure that specifies additional characteristics of the subresource update operation.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dumddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-d3dddiarg_copyflags.md">D3DDDIARG_COPYFLAGS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updatesubresourceup.md">pfnUpdateSubresourceUP</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddibox.md">D3DDDIBOX</a>