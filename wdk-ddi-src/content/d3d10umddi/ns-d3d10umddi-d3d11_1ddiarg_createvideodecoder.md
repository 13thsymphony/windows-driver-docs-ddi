---
UID: NS:d3d10umddi.D3D11_1DDIARG_CREATEVIDEODECODER
title: D3D11_1DDIARG_CREATEVIDEODECODER
author: windows-driver-content
description: Specifies the attributes of a video decoder object.
old-location: display\d3d11_1ddiarg_createvideodecoder.htm
old-project: display
ms.assetid: c309e9b1-b2bc-40bc-90b9-5c070ba48957
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D11_1DDIARG_CREATEVIDEODECODER, display.d3d11_1ddiarg_createvideodecoder, d3d10umddi/D3D11_1DDIARG_CREATEVIDEODECODER, D3D11_1DDIARG_CREATEVIDEODECODER structure [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3D11_1DDIARG_CREATEVIDEODECODER
product: Windows
targetos: Windows
req.typenames: D3D11_1DDIARG_CREATEVIDEODECODER
---

# D3D11_1DDIARG_CREATEVIDEODECODER structure
Specifies the attributes of a video decoder object.

## Syntax
````
typedef struct D3D11_1DDIARG_CREATEVIDEODECODER {
  D3D11_1DDI_VIDEO_DECODER_DESC   Desc;
  D3D11_1DDI_VIDEO_DECODER_CONFIG Config;
} D3D11_1DDIARG_CREATEVIDEODECODER;
````

## Members


`Config`

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md">D3D11_1DDI_VIDEO_DECODER_CONFIG</a> structure that specifies the decoder configuration.

`Desc`

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a> structure that describes the video stream and the decoder profile.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_config.md">D3D11_1DDI_VIDEO_DECODER_CONFIG</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDIARG_CREATEVIDEODECODER structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>