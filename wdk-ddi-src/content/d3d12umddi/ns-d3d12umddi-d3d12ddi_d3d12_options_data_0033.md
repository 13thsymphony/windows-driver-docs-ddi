---
UID: NS:d3d12umddi.D3D12DDI_D3D12_OPTIONS_DATA_0033
title: D3D12DDI_D3D12_OPTIONS_DATA_0033
author: windows-driver-content
description: Display options data.
old-location: display\d3d12ddi-d3d12-options-data-0033.htm
old-project: display
ms.assetid: d2b90ec1-cc4c-4a2b-8f7e-d46cd39d553b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3D12DDI_D3D12_OPTIONS_DATA_0033, D3D12DDI_D3D12_OPTIONS_DATA_0033 structure [Display Devices], d3d12umddi/D3D12DDI_D3D12_OPTIONS_DATA_0033, display.d3d12ddi-d3d12-options-data-0033
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
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
-	d3d12umddi.h
api_name:
-	D3D12DDI_D3D12_OPTIONS_DATA_0033
product: Windows
targetos: Windows
req.typenames: D3D12DDI_D3D12_OPTIONS_DATA_0033
---

# D3D12DDI_D3D12_OPTIONS_DATA_0033 structure
Display options data.

## Syntax
````
typedef struct _D3D12DDI_D3D12_OPTIONS_DATA_0033 {
  D3D12DDI_RESOURCE_BINDING_TIER               ResourceBindingTier;
  D3D12DDI_CONSERVATIVE_RASTERIZATION_TIER     ConservativeRasterizationTier;
  D3D12DDI_TILED_RESOURCES_TIER                TiledResourcesTier;
  D3D12DDI_CROSS_NODE_SHARING_TIER             CrossNodeSharingTier;
  BOOL                                         VPAndRTArrayIndexFromAnyShaderFeedingRasterizerSupportedWithoutGSEmulation;
  BOOL                                         OutputMergerLogicOp;
  D3D12DDI_RESOURCE_HEAP_TIER                  ResourceHeapTier;
  BOOL                                         DepthBoundsTestSupported;
  D3D12DDI_PROGRAMMABLE_SAMPLE_POSITIONS_TIER  ProgrammableSamplePositionsTier;
  BOOL                                         CopyQueueTimestampQueriesSupported;
  D3D12DDI_COMMAND_QUEUE_FLAGS                 WriteBufferImmediateQueueFlags;
  D3D12DDI_VIEW_INSTANCING_TIER                ViewInstancingTier;
  BOOL                                         BarycentricsSupported;
} D3D12DDI_D3D12_OPTIONS_DATA_0033, D3D12DDI_D3D12_OPTIONS_DATA_0033;
````

## Members


`BarycentricsSupported`

Barycentrics supported.

`ConservativeRasterizationTier`

Conservative rasterization tier.

`CopyQueueTimestampQueriesSupported`

Copy queue timestamp queries supported.

`CrossNodeSharingTier`

Cross node sharing tier.

`DepthBoundsTestSupported`

Depth bounds test supported.

`OutputMergerLogicOp`

Output merger logic option.

`ProgrammableSamplePositionsTier`

Programmable sample positions tier.

`ResourceBindingTier`

Resource binding tier.

`ResourceHeapTier`

Resource heap tier.

`TiledResourcesTier`

Tiled resource tier.

`ViewInstancingTier`

View instancing tier.

`VPAndRTArrayIndexFromAnyShaderFeedingRasterizerSupportedWithoutGSEmulation`

VP and RT array index from any shader feeding rasterizer supported without GS emulation.

`WriteBufferImmediateQueueFlags`

Write buffer immediate queue flags.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h |