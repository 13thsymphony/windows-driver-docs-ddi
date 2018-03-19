---
UID: NS:d3d10umddi.D3D10DDIARG_CREATEQUERY
title: D3D10DDIARG_CREATEQUERY
author: windows-driver-content
description: The D3D10DDIARG_CREATEQUERY structure describes the query to create.
old-location: display\d3d10ddiarg_createquery.htm
old-project: display
ms.assetid: 1042f401-fbdd-47ee-8cfc-1bca331ac722
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10DDIARG_CREATEQUERY, D3D10DDIARG_CREATEQUERY structure [Display Devices], UMDisplayDriver_Dx10param_Structs_92f45053-c4aa-4bcd-b2ab-570aaf95cfe3.xml, d3d10umddi/D3D10DDIARG_CREATEQUERY, display.d3d10ddiarg_createquery
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	D3D10DDIARG_CREATEQUERY
product: Windows
targetos: Windows
req.typenames: D3D10DDIARG_CREATEQUERY
---

# D3D10DDIARG_CREATEQUERY structure
The D3D10DDIARG_CREATEQUERY structure describes the query to create.

## Syntax
````
typedef struct D3D10DDIARG_CREATEQUERY {
  D3D10DDI_QUERY Query;
  UINT           MiscFlags;
} D3D10DDIARG_CREATEQUERY;
````

## Members


`Query`

[in] A <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a>-typed value that identifies the type of query to create.

`MiscFlags`

[in] A valid bitwise OR of flag values for the query. Currently, the Direct3D runtime supports only the D3D10DDI_QUERY_MISCFLAG_PREDICATEHINT (0x1) flag. This flag is set along with a D3DQUERYTYPE_OCCLUSIONPREDICATE query type to indicate that the predicate query is a hint. If a predicate query is indicated as a hint (versus guaranteed), no result is ever propagated back to the calling application.

## Remarks
The Direct3D runtime calls the user-mode display driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function with a query type to create resources for a query. For information about the type of resources the user-mode display driver creates, see the values of the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a> enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivatequerysize.md">CalcPrivateQuerySize</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a>