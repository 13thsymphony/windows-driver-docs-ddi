---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
title: D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
author: windows-driver-content
description: Describes the video decoder capabilities.
old-location: display\d3dwddm2_0ddi_video_decoder_caps.htm
old-project: display
ms.assetid: 1C3E07CB-917D-4B3E-979D-4DBD38957B98
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DWDDM2_0DDI_VIDEO_DECODER_CAP_UNSUPPORTED, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAP_NON_REAL_TIME, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE_REQUIRED, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE_REQUIRED, D3DWDDM2_0DDI_VIDEO_DECODER_CAP_NON_REAL_TIME, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAP_UNSUPPORTED, display.d3dwddm2_0ddi_video_decoder_caps, d3d10umddi/D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE, D3DWDDM2_0DDI_VIDEO_DECODER_CAPS enumeration [Display Devices], D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
-	D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_DECODER_CAPS
---

# D3DWDDM2_0DDI_VIDEO_DECODER_CAPS Enumeration
Describes the video decoder capabilities.

## Syntax
````
typedef enum D3DWDDM2_0DDI_VIDEO_DECODER_CAPS { 
  D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE           = 0x01,
  D3DWDDM2_0DDI_VIDEO_DECODER_CAP_NON_REAL_TIME        = 0x02,
  D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE_REQUIRED  = 0x04,
  D3DWDDM2_0DDI_VIDEO_DECODER_CAP_UNSUPPORTED          = 0x08
} D3DWDDM2_0DDI_VIDEO_DECODER_CAPS;
````

## Constants

<table>
            
                <tr>
                    <td>D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE</td>
                    <td>Indicates that the driver can support at least some downsampling scenarios.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_VIDEO_DECODER_CAP_DOWNSAMPLE_REQUIRED</td>
                    <td>Indicates that the decode configuration can be supported only if down sampling is applied.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_VIDEO_DECODER_CAP_NON_REAL_TIME</td>
                    <td>The decode operation is supported, but cannot be performed real-time.  Indicates that the decode hardware cannot support the decode operation in real-time. Decode is still viable for transcode scenarios. 



It is possible that decode can occur in real-time if downsampling is applied.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_VIDEO_DECODER_CAP_UNSUPPORTED</td>
                    <td>Indicates that the decode configuration is not supported.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

    ## See Also

        <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_queryvideocapabilities.md">QueryVideoCapabilities</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM2_0DDI_VIDEO_DECODER_CAPS enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>