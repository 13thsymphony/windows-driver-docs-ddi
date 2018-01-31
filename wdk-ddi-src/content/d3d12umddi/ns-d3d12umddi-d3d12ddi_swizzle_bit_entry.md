---
UID : NS:d3d12umddi.D3D12DDI_SWIZZLE_BIT_ENTRY
title : D3D12DDI_SWIZZLE_BIT_ENTRY
author : windows-driver-content
description : Defines a swizzle bit entry.
old-location : display\d3d12ddi_swizzle_bit_entry.htm
old-project : display
ms.assetid : B7FF7AA2-39B2-4D9E-8DDC-0A39FFF49F37
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_SWIZZLE_BIT_ENTRY structure [Display Devices], d3d12umddi/D3D12DDI_SWIZZLE_BIT_ENTRY, D3D12DDI_SWIZZLE_BIT_ENTRY, display.d3d12ddi_swizzle_bit_entry
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
req.typenames : D3D12DDI_SWIZZLE_BIT_ENTRY
---

# D3D12DDI_SWIZZLE_BIT_ENTRY structure
Defines a swizzle bit entry.

## Syntax
````
typedef struct D3D12DDI_SWIZZLE_BIT_ENTRY {
  UINT8 Valid  :1;
  UINT8 ChannelIndex  :2;
  UINT8 SourceBitIndex  :5;
} D3D12DDI_SWIZZLE_BIT_ENTRY;
````

## Members


`ChannelIndex`

The channel index. Specify zero (0) for X, one (1) for Y, two (2) for Z, and three (3) for SS.

`SourceBitIndex`

Index of source bit address.

`Valid`

A valid value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |