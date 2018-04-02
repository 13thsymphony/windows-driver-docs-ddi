---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022
title: D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022
author: windows-driver-content
description: Specifies information used to retrieve capabilities for a video processor.
old-location: display\d3d12ddi_video_process_support_data.htm
old-project: display
ms.assetid: B42D3637-BBFF-411B-AA1B-4B9578E2EDA9
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022, D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022, display.d3d12ddi_video_process_support_data
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
-	D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022
---

# D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022 structure
Specifies information used to retrieve capabilities for a video processor.

## Syntax
```
typedef struct D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022 {
  UINT                                              NodeIndex;
  D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020            InputSample;
  D3D12DDI_VIDEO_FIELD_TYPE_0020                    InputFieldType;
  D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020           InputStereoFormat;
  DXGI_RATIONAL                                     InputFrameRate;
  D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020            OutputFormat;
  D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020           OutputStereoFormat;
  DXGI_RATIONAL                                     OutputFrameRate;
  D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022         SupportFlags;
  D3D12DDI_VIDEO_SCALE_SUPPORT_0022                 ScaleSupport;
  D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS_0020 FeatureSupport;
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020     DeinterlaceSupport;
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022 AutoProcessingSupport;
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020          FilterSupport;
  D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020          FilterRangeSupport[D3D12DDI_VIDEO_PROCESS_MAX_FILTERS_0020];
};
```

## Members


`NodeIndex`

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

`InputSample`

The input width, height, and format.  For more information, see the <a href="https://msdn.microsoft.com/B9918A06-6C10-4AD7-97EC-4FA0BC5319AD">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a> structure.

`InputFieldType`

The interlaced field type of the input sample.  For more information, see the <a href="https://msdn.microsoft.com/869BF62F-C8FE-4AD8-A413-65FBE97EE7FB">D3D12DDI_VIDEO_FIELD_TYPE</a> enumeration.

`InputStereoFormat`

The stereo format of the input.  For more information, see the <a href="https://msdn.microsoft.com/91C5C387-320C-4ABE-98AB-36D2CDE7428F">D3D12DDI_VIDEO_FRAME_STEREO_FORMAT</a> enumeration.

`InputFrameRate`

The input frame rate.

`OutputFormat`

The output DXGI format and color space.  For more information, see the <a href="https://msdn.microsoft.com/47C0C369-B31B-4291-A420-A1E75BA990CF">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a> structure.

`OutputStereoFormat`

The stereo format of the output.  For more information, see the <a href="https://msdn.microsoft.com/91C5C387-320C-4ABE-98AB-36D2CDE7428F">D3D12DDI_VIDEO_FRAME_STEREO_FORMAT</a> enumeration.

`OutputFrameRate`

The frame rate of the output.

`SupportFlags`

Indicates whether the conversion from input format and colorspace to output format and color space is supported.  For more information, see the <a href="https://msdn.microsoft.com/2E6E1F22-C6E8-4290-A342-B01387633D43">D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS</a> enumeration.

`ScaleSupport`

Indicates the supported output scale range for the  input to output processing.  For more information, see the <a href="https://msdn.microsoft.com/70FFDE9E-2029-4C84-9DEE-C2E81FEE5590">D3D12DDI_VIDEO_SCALE_SUPPORT</a> structure.

`FeatureSupport`

A bitwise OR of zero or more flags from the <a href="https://msdn.microsoft.com/6DBF48B1-44C7-4C53-8488-F1217E6FAA1C">D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS</a> enumeration.

`DeinterlaceSupport`

The deinterlace modes supported by the driver as a bitwise OR of zero or more flags from the <a href="https://msdn.microsoft.com/7E34CCE5-A771-4EBE-A09B-79424405BFF3">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a> enumeration.

`AutoProcessingSupport`

Indicates the type of auto processing operations supported by driver.

`FilterSupport`

A bitwise OR of zero or more flags from the <a href="https://msdn.microsoft.com/28662E87-F6A4-42B0-9BF0-49A6C65B245C">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.

`FilterRangeSupport`

The list of filter range values.  The order of the range values should be specified in the same order that the filters appear in the <a href="https://msdn.microsoft.com/28662E87-F6A4-42B0-9BF0-49A6C65B245C">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.  <b>D3D12DDI_VIDEO_PROCESS_MAX_FILTERS</b> range values are available for current and future filters.  The D3D runtime zero initializes any range value that is not supported by the driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/869BF62F-C8FE-4AD8-A413-65FBE97EE7FB">D3D12DDI_VIDEO_FIELD_TYPE</a>



<a href="https://msdn.microsoft.com/47C0C369-B31B-4291-A420-A1E75BA990CF">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/91C5C387-320C-4ABE-98AB-36D2CDE7428F">D3D12DDI_VIDEO_FRAME_STEREO_FORMAT</a>



<a href="https://msdn.microsoft.com/7E34CCE5-A771-4EBE-A09B-79424405BFF3">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a>



<a href="https://msdn.microsoft.com/6DBF48B1-44C7-4C53-8488-F1217E6FAA1C">D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS</a>



<a href="https://msdn.microsoft.com/28662E87-F6A4-42B0-9BF0-49A6C65B245C">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a>



<a href="https://msdn.microsoft.com/2E6E1F22-C6E8-4290-A342-B01387633D43">D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS</a>



<a href="https://msdn.microsoft.com/B9918A06-6C10-4AD7-97EC-4FA0BC5319AD">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a>



<a href="https://msdn.microsoft.com/70FFDE9E-2029-4C84-9DEE-C2E81FEE5590">D3D12DDI_VIDEO_SCALE_SUPPORT</a>