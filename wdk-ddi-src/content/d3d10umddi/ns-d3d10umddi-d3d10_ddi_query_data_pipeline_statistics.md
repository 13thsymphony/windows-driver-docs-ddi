---
UID : NS:d3d10umddi.D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS
title : D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS
author : windows-driver-content
description : The D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the CreateQuery(D3D10) function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the QueryGetData function to return information about the query.
old-location : display\d3d10_ddi_query_data_pipeline_statistics.htm
old-project : display
ms.assetid : 5e481453-1e01-46b4-a04e-e9c575cd65b9
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS, D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS
req.alt-loc : d3d10umddi.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS
---

# D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure
The D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure describes statistics for each stage of the graphics pipeline that is used in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a> function to create a D3D10DDI_QUERY_PIPELINESTATS query type and in a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a> function to return information about the query.

## Syntax
````
typedef struct D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS {
  UINT64 IAVertices;
  UINT64 IAPrimitives;
  UINT64 VSInvocations;
  UINT64 GSInvocations;
  UINT64 GSPrimitives;
  UINT64 CInvocations;
  UINT64 CPrimitives;
  UINT64 PSInvocations;
} D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS;
````

## Members

        
            `CInvocations`

            The number of clipper invocations.
        
            `CPrimitives`

            The number of clipper primitives.
        
            `GSInvocations`

            The number of geometry shader (GS) invocations.
        
            `GSPrimitives`

            The number of GS primitives.
        
            `IAPrimitives`

            The number of IA primitives.
        
            `IAVertices`

            The number of input assembler (IA) veritces.
        
            `PSInvocations`

            The number of pixel shader (PS) invocations.
        
            `VSInvocations`

            The number of vertex shader (VS) invocations.

    ## Remarks
        The driver associates a D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure with the D3D10DDI_QUERY_PIPELINESTATS query type value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a> enumeration.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createquery.md">CreateQuery(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10ddi_query.md">D3D10DDI_QUERY</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_querygetdata.md">QueryGetData</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D10_DDI_QUERY_DATA_PIPELINE_STATISTICS structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>