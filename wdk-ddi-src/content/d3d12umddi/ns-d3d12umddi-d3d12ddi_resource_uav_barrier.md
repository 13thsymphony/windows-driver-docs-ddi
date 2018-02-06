---
UID: NS:d3d12umddi.D3D12DDI_RESOURCE_UAV_BARRIER
title: D3D12DDI_RESOURCE_UAV_BARRIER
author: windows-driver-content
description: Contains an unordered access view (UAV) barrier.
old-location: display\d3d12ddi_resource_uav_barrier.htm
old-project: display
ms.assetid: 8473EB26-54C5-49D0-A854-422086CE8CCC
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.d3d12ddi_resource_uav_barrier, D3D12DDI_RESOURCE_UAV_BARRIER structure [Display Devices], D3D12DDI_RESOURCE_UAV_BARRIER, d3d12umddi/D3D12DDI_RESOURCE_UAV_BARRIER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	D3d12umddi.h
apiname:
-	D3D12DDI_RESOURCE_UAV_BARRIER
product: Windows
targetos: Windows
req.typenames: D3D12DDI_RESOURCE_UAV_BARRIER
---

# D3D12DDI_RESOURCE_UAV_BARRIER structure
Contains an unordered access view (UAV) barrier.

## Syntax
````
typedef struct D3D12DDI_RESOURCE_UAV_BARRIER {
  D3D12DDI_HRESOURCE hResource;
} D3D12DDI_RESOURCE_UAV_BARRIER;
````

## Members


`hResource`

The handle of resource.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |