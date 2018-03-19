---
UID: NS:d3dhal._D3DHAL_DP2DELETEQUERY
title: "_D3DHAL_DP2DELETEQUERY"
author: windows-driver-content
description: DirectX 9.0 and later versions only.
old-location: display\d3dhal_dp2deletequery.htm
old-project: display
ms.assetid: c125e21f-20be-42c1-ba24-b13f2475f02e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2DELETEQUERY, D3DHAL_DP2DELETEQUERY, D3DHAL_DP2DELETEQUERY structure [Display Devices], LPD3DHAL_DP2DELETEQUERY, LPD3DHAL_DP2DELETEQUERY structure pointer [Display Devices], _D3DHAL_DP2DELETEQUERY, d3dhal/D3DHAL_DP2DELETEQUERY, d3dhal/LPD3DHAL_DP2DELETEQUERY, d3dstrct_3194de0d-21ee-4f44-9be3-2f2ebe6b06e2.xml, display.d3dhal_dp2deletequery"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	d3dhal.h
api_name:
-	D3DHAL_DP2DELETEQUERY
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2DELETEQUERY
---

# _D3DHAL_DP2DELETEQUERY structure
DirectX 9.0 and later versions only.
   

One or more D3DHAL_DP2DELETEQUERY structures are parsed from the command buffer by the <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback when the <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a> structure's <b>bCommand</b> member is set to D3DDP2OP_DELETEQUERY, and are used to release resources for queries.

## Syntax
````
typedef struct _D3DHAL_DP2DELETEQUERY {
  DWORD dwQueryID;
} D3DHAL_DP2DELETEQUERY, *LPD3DHAL_DP2DELETEQUERY;
````

## Members


`dwQueryID`

Identifies the query for which the driver releases resources.

## Remarks
The runtime uses D3DHAL_DP2DELETEQUERY to identify each query. The driver's <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> callback must process <b>wPrimitiveCount</b> D3DHAL_DP2DELETEQUERY structures from the command buffer. The value of <b>wPrimitiveCount</b> is specified in the D3DHAL_DP2COMMAND structure. The driver parses these structures and releases resources for the queries that they represent.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

D3DDP2OP_DELETEQUERY



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2createquery.md">D3DHAL_DP2CREATEQUERY</a>