---
UID: NE:d3d10umddi.D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
title: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
author: windows-driver-content
description: Describes the video capabilities to query.
old-location: display\d3dwddm2_0ddi_video_capability_query.htm
old-project: display
ms.assetid: A8BA3FF9-A821-43ED-91CB-EECD0ABA0954
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY enumeration [Display Devices], D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING, D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING, d3d10umddi/D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING, display.d3dwddm2_0ddi_video_capability_query
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d10umddi.h
api_name:
-	D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
product: Windows
targetos: Windows
req.typenames: D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY
---

# D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY Enumeration
Describes the video capabilities to query.

## Syntax
```
typedef enum D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY {
  D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING              ,
  D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING    ,
  D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS                      ,
  D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT
} ;
```

## Constants

<table>
            
                <tr>
                    <td>D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING</td>
                    <td>Indicates that the driver should return support for the specified down sampling parameters specified.



The input structure is of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn894615">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a>.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMEND_DECODER_DOWNSAMPLING</td>
                    <td>Indicates that the driver should recommend down sampling parameters.



The input structure is of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn894617">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a>.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS</td>
                    <td>Indicates that the driver should return video decoder capabilities.



The input structure is of type <a href="https://msdn.microsoft.com/library/windows/hardware/dn894614">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS</a>.</td>
                </tr>
            
                <tr>
                    <td>D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLE_OUTPUT_FORMAT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn894614">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_CAPS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn894615">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn894617">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a>