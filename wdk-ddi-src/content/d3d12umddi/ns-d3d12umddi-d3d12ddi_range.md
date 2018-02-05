---
UID : NS:d3d12umddi.D3D12DDI_RANGE
title : D3D12DDI_RANGE
author : windows-driver-content
description : Specifies a range.
old-location : display\d3d12ddi_range.htm
old-project : display
ms.assetid : B3A8F252-D56D-4F20-A0DE-2A29904BC907
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_RANGE structure [Display Devices], D3D12DDI_RANGE, display.d3d12ddi_range, d3d12umddi/D3D12DDI_RANGE
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
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
req.typenames : D3D12DDI_RANGE
---

# D3D12DDI_RANGE structure
Specifies a range.

## Syntax
````
typedef struct D3D12DDI_RANGE {
  UINT64 Begin;
  UINT64 End;
} D3D12DDI_RANGE;
````

## Members


`Begin`

The beginning of the range.

`End`

A value of one more than the end of the range. Therefore, the value of <i>End</i> minus the value of <i>Begin</i> is the size of the range.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |