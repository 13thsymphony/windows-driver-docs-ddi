---
UID: NS:d3d12umddi.D3D12DDI_DEVICE_FUNCS_VIDEO_0021
title: D3D12DDI_DEVICE_FUNCS_VIDEO_0021
author: windows-driver-content
description: Contains video functions.
old-location: display\d3d12ddi_device_funcs_video.htm
old-project: display
ms.assetid: F4C385C8-00A2-44AB-A7E6-4C9AA19CFFB0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_DEVICE_FUNCS_VIDEO_0021, D3D12DDI_DEVICE_FUNCS_VIDEO_0021 structure [Display Devices], d3d12umddi/D3D12DDI_DEVICE_FUNCS_VIDEO, display.d3d12ddi_device_funcs_video
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
-	D3D12DDI_DEVICE_FUNCS_VIDEO_0021
product: Windows
targetos: Windows
req.typenames: D3D12DDI_DEVICE_FUNCS_VIDEO_0021
---

# D3D12DDI_DEVICE_FUNCS_VIDEO_0021 structure
Contains video functions.

## Syntax
````
typedef struct D3D12DDI_DEVICE_FUNCS_VIDEO_0021 {
  PFND3D12DDI_VIDEO_GETCAPS                                    pfnGetCaps;
  PFND3D12DDI_CALCPRIVATEVIDEODECODERSIZE_0021                 pfnCalcPrivateVideoDecoderSize;
  PFND3D12DDI_CREATEVIDEODECODER_0021                          pfnCreateVideoDecoder;
  PFND3D12DDI_DESTROYVIDEODECODER_0021                         pfnDestroyVideoDecoder;
  PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0021               pfnCalcPrivateVideoProcessorSize;
  PFND3D12DDI_CREATEVIDEOPROCESSOR_0021                        pfnCreateVideoProcessor;
  PFND3D12DDI_DESTROYVIDEOPROCESSOR_0021                       pfnDestroyVideoProcessor;
  PFND3D12DDI_CALCPRIVATECONTENTPROTECTIONSESSIONSIZE_0020     pfnCalcPrivateContentProtectionSessionSize;
  PFND3D12DDI_CREATECONTENTPROTECTIONSESSION_0020              pfnCreateContentProtectionSession;
  PFND3D12DDI_DESTROYCONTENTPROTECTIONSESSION_0020             pfnDestroyContentProtectionSession;
  PFND3D12DDI_CONTENTPROTECTIONSESSION_INVOKE_FUNCTION_0020    pfnContentProtectionSessionInvokeFunction;
  PFND3D12DDI_CONTENTPROTECTIONSESSION_SETUP_HARDWARE_KEY_0020 pfnContentProtectionSessionSetupHardwareKey;
  PFND3D12DDI_CONTENTPROTECTIONSESSION_GET_STATUS_0020         pfnContentProtectionSessionGetStatus;
  PFND3D12DDI_VIDEO_GET_DECODE_PROFILE_COUNT_0020              pfnGetDecodeProfileCount;
  PFND3D12DDI_VIDEO_GET_DECODE_FORMAT_COUNT_0020               pfnGetDecodeFormatCount;
  PFND3D12DDI_VIDEO_GET_BITSTREAM_ENCRYPTION_SCHEME_COUNT_0020 pfnGetBitstreamEncryptionSchemeCount;
  PFND3D12DDI_VIDEO_DECODER_TRIM_ALLOCATIONS_0021              pfnDecoderTrimAllocations;
  PFND3D12DDI_VIDEO_PROCESSOR_TRIM_ALLOCATIONS_0021            pfnProcessorTrimAllocations;
} D3D12DDI_DEVICE_FUNCS_VIDEO_0021;
````

## Members


`pfnCalcPrivateContentProtectionSessionSize`

A function that calculates the size of a private content protection session.

`pfnCalcPrivateVideoDecoderSize`

A function that calculates the size of a private decoder.

`pfnCalcPrivateVideoProcessorSize`

A function that calculates the size of a private video processor.

`pfnContentProtectionSessionGetStatus`

A function that gets the status of a content protection session.

`pfnContentProtectionSessionInvokeFunction`

A function that invokes a function in a content protection session.

`pfnContentProtectionSessionSetupHardwareKey`

A function that sets up a hardware key for a content protection session.

`pfnCreateContentProtectionSession`

A function that creates a content protection system.

`pfnCreateVideoDecoder`

A function that creates a video decoder.

`pfnCreateVideoProcessor`

A function that creates a video processor.

`pfnDecoderTrimAllocations`

A function that trims decoder allocations.

`pfnDestroyContentProtectionSession`

A function that destroys a content protection system.

`pfnDestroyVideoDecoder`

A function that destroys a video decoder.

`pfnDestroyVideoProcessor`

A function that destroys a video processor.

`pfnGetBitstreamEncryptionSchemeCount`

A function that gets the count of bitstream encryption schemes.

`pfnGetCaps`

A function that gets video capabilities.

`pfnGetDecodeFormatCount`

A function that gets the decode format count.

`pfnGetDecodeProfileCount`

A function that gets the decode profile count.

`pfnProcessorTrimAllocations`

A function that trims processor allocations.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddi_device_funcs_core_0010.md">D3D12DDI_DEVICE_FUNCS_CORE_0010</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_DEVICE_FUNCS_VIDEO_0021 structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>