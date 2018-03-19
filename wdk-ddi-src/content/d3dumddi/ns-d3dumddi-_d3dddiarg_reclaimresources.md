---
UID: NS:d3dumddi._D3DDDIARG_RECLAIMRESOURCES
title: "_D3DDDIARG_RECLAIMRESOURCES"
author: windows-driver-content
description: Describes video memory resources that are to be reclaimed and that the user-mode display driver previously offered for reuse. Used with the ReclaimResources function.
old-location: display\d3dddiarg_reclaimresources.htm
old-project: display
ms.assetid: 58e8738c-b10a-4c93-b179-03efcb65412d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_RECLAIMRESOURCES, D3DDDIARG_RECLAIMRESOURCES structure [Display Devices], _D3DDDIARG_RECLAIMRESOURCES, d3dumddi/D3DDDIARG_RECLAIMRESOURCES, display.d3dddiarg_reclaimresources
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: 
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
-	D3dumddi.h
api_name:
-	D3DDDIARG_RECLAIMRESOURCES
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_RECLAIMRESOURCES
---

# _D3DDDIARG_RECLAIMRESOURCES structure
Describes video memory resources that are to be reclaimed and that the user-mode display driver  previously offered  for reuse. Used with the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimresources.md">ReclaimResources</a> function.

## Syntax
````
typedef struct _D3DDDIARG_RECLAIMRESOURCES {
  HANDLE *pResources;
  BOOL   *pDiscarded;
  UINT   Resources;
} D3DDDIARG_RECLAIMRESOURCES;
````

## Members


`pResources`

[in] A pointer to an array of handles to the resources that are to be reclaimed.

`pDiscarded`

[out] An optional array of Boolean values that specify whether each resource or allocation was discarded.

Each Boolean value in this array corresponds to a resource at the same index location in the structure pointed to by <b>pResources</b>.

The driver sets each Boolean value to <b>TRUE</b> if the corresponding resource was discarded, or to <b>FALSE</b> if not.

If <b>pDiscarded</b> is <b>NULL</b>, the driver can ignore it.

`Resources`

[in] The number of elements in the arrays pointed to by <b>pResources</b> and <b>pDiscarded</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3dumddi.h |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reclaimresources.md">ReclaimResources</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>