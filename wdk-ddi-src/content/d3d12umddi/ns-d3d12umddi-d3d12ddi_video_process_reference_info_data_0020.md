---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
title: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
author: windows-driver-content
description: Data structure for D3D12DDICAPS_VIDEO_PROCESS_REFERENCE_INFO capability check. Retrieves the number of past and future frames required for a given deinterlace mode.
old-location: display\d3d12ddi_video_process_reference_info_data.htm
old-project: display
ms.assetid: 3711ACBD-482E-4BB8-8530-C92DA610CA5B
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020, D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020, display.d3d12ddi_video_process_reference_info_data
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020
---

# D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 structure
Data structure for D3D12DDICAPS_VIDEO_PROCESS_REFERENCE_INFO capability check.  Retrieves the number of past and future frames required for a given deinterlace mode.

## Syntax
```
typedef struct D3D12DDI_VIDEO_PROCESS_REFERENCE_INFO_DATA_0020 {
  UINT                                              NodeIndex;
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020     DeinterlaceMode;
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020          Filters;
  D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS_0020 FeatureSupport;
  DXGI_RATIONAL                                     InputFrameRate;
  DXGI_RATIONAL                                     OutputFrameRate;
  BOOL                                              EnableAutoProcessing;
  UINT                                              PastFrames;
  UINT                                              FutureFrames;
};
```

## Members


`NodeIndex`

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

`DeinterlaceMode`

The deinterlacing mode for which to retrieve the number of past and future frames.  Only a single mode may be queried at once.  For more information, see the <a href="https://msdn.microsoft.com/7E34CCE5-A771-4EBE-A09B-79424405BFF3">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a> enumeration.

`Filters`

The filters for which to retrieve the number of past and future frames.  You can specify multiple filters may be specified.  For more information, see the <a href="https://msdn.microsoft.com/28662E87-F6A4-42B0-9BF0-49A6C65B245C">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.

`FeatureSupport`

The features for which to retrieve the number of past and future frames.  For more information, see the  <a href="https://msdn.microsoft.com/6DBF48B1-44C7-4C53-8488-F1217E6FAA1C">D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS</a> enumeration.

`InputFrameRate`



`OutputFrameRate`



`EnableAutoProcessing`

Whether automatic processing is used.

`PastFrames`

The number of past reference frames required to support this processing.

`FutureFrames`

The number of future reference frames required to support this processing.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/7E34CCE5-A771-4EBE-A09B-79424405BFF3">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a>



<a href="https://msdn.microsoft.com/6DBF48B1-44C7-4C53-8488-F1217E6FAA1C">D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS</a>



<a href="https://msdn.microsoft.com/28662E87-F6A4-42B0-9BF0-49A6C65B245C">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a>