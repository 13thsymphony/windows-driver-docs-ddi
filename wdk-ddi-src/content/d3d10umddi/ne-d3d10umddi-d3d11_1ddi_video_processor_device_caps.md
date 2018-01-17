---
UID: NE:d3d10umddi.D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS
title: D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS
author: windows-driver-content
description: Defines video processing capabilities for a Microsoft Direct3D 11 video processor.
old-location: display\d3d11_1ddi_video_processor_device_caps.htm
old-project: display
ms.assetid: ce2bdf90-45c1-4a4b-bc6e-276536460324
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS, D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS
req.alt-loc: D3d10umddi.h
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
req.typenames: D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS
---

# D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS enumeration



## -description
Defines video processing capabilities for a Microsoft Direct3D 11 video processor.



## -syntax

````
typedef enum D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS { 
  D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_LINEAR_SPACE             = 0x1,
  D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_xvYCC                    = 0x2,
  D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_RGB_RANGE_CONVERSION     = 0x4,
  D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_YCbCr_MATRIX_CONVERSION  = 0x8,
  D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_NOMINAL_RANGE            = 0x10
} D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS;
````


## -enum-fields

### -field D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_LINEAR_SPACE

The video processor can blend video content in linear color space. Most video content is gamma corrected, resulting in nonlinear values. This capability flag means that the video processor converts colors to linear space before blending, which produces better results.


### -field D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_xvYCC

The video processor supports the xvYCC color space for YCbCr data.


### -field D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_RGB_RANGE_CONVERSION

The video processor can perform range conversion when the input and output are both RGB but use different color ranges (0–255 or 16–235, for 8-bit RGB).


### -field D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_YCbCr_MATRIX_CONVERSION

The video processor can apply a matrix conversion to YCbCr values when the input and output are both YCbCr. For example, the driver can convert colors from BT.601 to BT.709. 




### -field D3D11_1DDI_VIDEO_PROCESSOR_DEVICE_CAPS_NOMINAL_RANGE

The video processor can convert between luminance ranges when the input and output use different luminance ranges.

Supported starting with Windows 8.1.


## -remarks
