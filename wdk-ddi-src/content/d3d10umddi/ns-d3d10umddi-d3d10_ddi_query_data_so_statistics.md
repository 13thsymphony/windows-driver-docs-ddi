---
UID: NS:d3d10umddi.D3D10_DDI_QUERY_DATA_SO_STATISTICS
title: D3D10_DDI_QUERY_DATA_SO_STATISTICS
author: windows-driver-content
description: The D3D10_DDI_QUERY_DATA_SO_STATISTICS structure describes stream output statistics that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_STREAMOUTPUTSTATS query type and in a call to the QueryGetData function to return information about the query.
old-location: display\d3d10_ddi_query_data_so_statistics.htm
old-project: display
ms.assetid: 641c8f8d-e398-4ca4-9e28-bba2ef7d1bd3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10_DDI_QUERY_DATA_SO_STATISTICS, D3D10_DDI_QUERY_DATA_SO_STATISTICS structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3748a5db-9ce8-4763-baac-4110b754188d.xml, d3d10umddi/D3D10_DDI_QUERY_DATA_SO_STATISTICS, display.d3d10_ddi_query_data_so_statistics
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
-	D3D10_DDI_QUERY_DATA_SO_STATISTICS
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_QUERY_DATA_SO_STATISTICS
---

# D3D10_DDI_QUERY_DATA_SO_STATISTICS structure
The D3D10_DDI_QUERY_DATA_SO_STATISTICS structure describes stream output statistics that is used in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_STREAMOUTPUTSTATS 

query type and in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function to return information about the query.

## Syntax
````
typedef struct D3D10_DDI_QUERY_DATA_SO_STATISTICS {
  UINT64 NumPrimitivesWritten;
  UINT64 PrimitivesStorageNeeded;
} D3D10_DDI_QUERY_DATA_SO_STATISTICS;
````

## Members


`NumPrimitivesWritten`

The number of primitives that is written to the stream output resource.

`PrimitivesStorageNeeded`

The number of primitives that would have been written to the stream output resource if the resource was big enough.

## Remarks
The driver associates a D3D10_DDI_QUERY_DATA_SO_STATISTICS structure with the D3D10DDI_QUERY_STREAMOUTPUTSTATS query type value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a> enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a>