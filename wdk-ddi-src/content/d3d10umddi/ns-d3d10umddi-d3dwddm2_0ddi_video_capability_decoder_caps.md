---
UID: NS:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
author: windows-driver-content
description: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS contains information describing the capabilities of the video decoder.
old-location: display\d3dwddm2_0ddi_video_capability_decoder_caps.htm
old-project: display
ms.assetid: C248B20E-A9A1-4C79-9053-16AC2059205E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS structure [Display Devices], D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS, display.d3dwddm2_0ddi_video_capability_decoder_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	D3d10umddi.h
apiname:
-	D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS structure
<b>D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS</b> contains information describing the capabilities of the video decoder.

## Syntax
````
typedef struct D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS {
  GUID          DecodeProfile;
  UINT          SampleWidth;
  UINT          SampleHeight;
  DXGI_RATIONAL FrameRate;
  UINT          Caps;
} D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS;
````

## Members


`BitRate`



`Caps`

Returns a combination of <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_video_decoder_caps.md">D3DWDDM2_0DDI_VIDEO_DECODER_CAPS</a> enumeration values combined together using a bitwise <i>OR</i> operation.

`DecodeProfile`

Indicates the decode profile for which the capabilities are queried.

`FrameRate`

Indicates the frame rate of the video content.

`pCryptoType`



`SampleHeight`

Indicates the video height for which the capabilities are queried.

`SampleWidth`

Indicates the video width for which the capabilities are queried.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |