---
UID : NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022
title : D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022
author : windows-driver-content
description : Specifies information used to retrieve capabilities for a video processor.
old-location : display\d3d12ddi_video_process_support_data.htm
old-project : display
ms.assetid : B42D3637-BBFF-411B-AA1B-4B9578E2EDA9
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : d3d12umddi/D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022, D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022 structure [Display Devices], display.d3d12ddi_video_process_support_data, D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022
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
req.typenames : D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022
---

# D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022 structure
Specifies information used to retrieve capabilities for a video processor.

## Syntax
````
typedef struct D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022 {
  UINT                                              NodeIndex;
  D3D12DDI_VIDEO_SAMPLE_DESCRIPTION_0020            InputSample;
  D3D12DDI_VIDEO_FIELD_TYPE_0020                    InputFieldType;
  D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020           InputStereoFormat;
  DXGI_RATIONAL                                     InputFrameRate;
  D3D12DDI_VIDEO_FORMAT_DESCRIPTION_0020            OutputFormat;
  D3D12DDI_VIDEO_FRAME_STEREO_FORMAT_0020           OutputStereoFormat;
  DXGI_RATIONAL                                     OutputFrameRate;
  D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS_0022         SupportFlags;
  D3D12DDI_VIDEO_SCALE_SUPPORT_0022                 ScaleSupport;
  D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS_0020 FeatureSupport;
  D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS_0020     DeinterlaceSupport;
  D3D12DDI_VIDEO_PROCESS_AUTO_PROCESSING_FLAGS_0022 AutoProcessingSupport;
  D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS_0020          FilterSupport;
  D3D12DDI_VIDEO_PROCESS_FILTER_RANGE_0020          FilterRangeSupport[D3D12DDI_VIDEO_PROCESS_MAX_FILTERS];
} D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022;
````

## Members


`AutoProcessingSupport`

Indicates the type of auto processing operations supported by driver.

`DeinterlaceSupport`

The deinterlace modes supported by the driver as a bitwise OR of zero or more flags from the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a> enumeration.

`FeatureSupport`

A bitwise OR of zero or more flags from the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_feature_support_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS</a> enumeration.

`FilterRangeSupport`

The list of filter range values.  The order of the range values should be specified in the same order that the filters appear in the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.  <b>D3D12DDI_VIDEO_PROCESS_MAX_FILTERS</b> range values are available for current and future filters.  The D3D runtime zero initializes any range value that is not supported by the driver.

`FilterSupport`

A bitwise OR of zero or more flags from the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a> enumeration.

`InputFieldType`

The interlaced field type of the input sample.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_field_type_0020.md">D3D12DDI_VIDEO_FIELD_TYPE</a> enumeration.

`InputFrameRate`

The input frame rate.

`InputSample`

The input width, height, and format.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_sample_description_0020.md">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a> structure.

`InputStereoFormat`

The stereo format of the input.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_frame_stereo_format_0020.md">D3D12DDI_VIDEO_FRAME_STEREO_FORMAT</a> enumeration.

`NodeIndex`

In multi-adapter operation, this indicates which physical adapter of the device this operation applies to.

`OutputFormat`

The output DXGI format and color space.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_format_description_0020.md">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a> structure.

`OutputFrameRate`

The frame rate of the output.

`OutputStereoFormat`

The stereo format of the output.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_frame_stereo_format_0020.md">D3D12DDI_VIDEO_FRAME_STEREO_FORMAT</a> enumeration.

`ScaleSupport`

Indicates the supported output scale range for the  input to output processing.  For more information, see the <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_scale_support_0022.md">D3D12DDI_VIDEO_SCALE_SUPPORT</a> structure.

`SupportFlags`

Indicates whether the conversion from input format and colorspace to output format and color space is supported.  For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_support_flags_0022.md">D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS</a> enumeration.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_deinterlace_flags_0020.md">D3D12DDI_VIDEO_PROCESS_DEINTERLACE_FLAGS</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_support_flags_0022.md">D3D12DDI_VIDEO_PROCESS_SUPPORT_FLAGS</a>

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_sample_description_0020.md">D3D12DDI_VIDEO_SAMPLE_DESCRIPTION</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_filter_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FILTER_FLAGS</a>

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_scale_support_0022.md">D3D12DDI_VIDEO_SCALE_SUPPORT</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_frame_stereo_format_0020.md">D3D12DDI_VIDEO_FRAME_STEREO_FORMAT</a>

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_video_format_description_0020.md">D3D12DDI_VIDEO_FORMAT_DESCRIPTION</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_field_type_0020.md">D3D12DDI_VIDEO_FIELD_TYPE</a>

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_process_feature_support_flags_0020.md">D3D12DDI_VIDEO_PROCESS_FEATURE_SUPPORT_FLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_PROCESS_SUPPORT_DATA_0022 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>