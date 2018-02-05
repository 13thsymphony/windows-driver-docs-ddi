---
UID : NE:d3d12umddi.D3D12DDI_QUERY_HEAP_TYPE
title : D3D12DDI_QUERY_HEAP_TYPE
author : windows-driver-content
description : Type of a query heap, which is an array of query results.
old-location : display\d3d12ddi_query_heap_type.htm
old-project : display
ms.assetid : 8A1A42B5-D978-4019-825B-94DB81C44FEA
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION, D3D12DDI_QUERY_HEAP_TYPE enumeration [Display Devices], display.d3d12ddi_query_heap_type, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION, D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP, D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE, D3D12DDI_QUERY_HEAP_TYPE, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS, d3d12umddi/D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS, D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d12umddi.h
req.include-header : D3d12umddi.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : D3D12DDI_QUERY_HEAP_TYPE
---

# D3D12DDI_QUERY_HEAP_TYPE Enumeration
Type of a query heap, which is an array of query results.

## Syntax
````
typedef enum D3D12DDI_QUERY_HEAP_TYPE { 
  D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION                     = 0,
  D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP                     = 1,
  D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS           = 2,
  D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS                 = 3,
  D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS  = 4,
  D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP     = 5
} D3D12DDI_QUERY_HEAP_TYPE;
````

## Constants

<table>

<tr>
<td>D3D12DDI_QUERY_HEAP_TYPE_0020_VIDEO_DECODE_STATISTICS</td>
<td>Video decode statistics.</td>
</tr>

<tr>
<td>D3D12DDI_QUERY_HEAP_TYPE_0032_COPY_QUEUE_TIMESTAMP</td>
<td>Copy queue timestamp.</td>
</tr>

<tr>
<td>D3D12DDI_QUERY_HEAP_TYPE_OCCLUSION</td>
<td>Occlusion.</td>
</tr>

<tr>
<td>D3D12DDI_QUERY_HEAP_TYPE_PIPELINE_STATISTICS</td>
<td>Pipeline statistics.</td>
</tr>

<tr>
<td>D3D12DDI_QUERY_HEAP_TYPE_SO_STATISTICS</td>
<td>SO statistics.</td>
</tr>

<tr>
<td>D3D12DDI_QUERY_HEAP_TYPE_TIMESTAMP</td>
<td>Timestamp.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |