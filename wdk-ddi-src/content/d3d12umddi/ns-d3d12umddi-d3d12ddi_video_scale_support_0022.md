---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SCALE_SUPPORT_0022
title: D3D12DDI_VIDEO_SCALE_SUPPORT_0022
author: windows-driver-content
description: Describes a supported range of output sizes for a scaler.
old-location: display\d3d12ddi_video_scale_support.htm
old-project: display
ms.assetid: 70FFDE9E-2029-4C84-9DEE-C2E81FEE5590
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_SCALE_SUPPORT_0022, D3D12DDI_VIDEO_SCALE_SUPPORT_0022
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
req.alt-api: D3D12DDI_VIDEO_SCALE_SUPPORT_0022
req.alt-loc: D3d12umddi.h
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
req.typenames: D3D12DDI_VIDEO_SCALE_SUPPORT_0022
---

# D3D12DDI_VIDEO_SCALE_SUPPORT_0022 structure



## -description
Describes a supported range of output sizes for a scaler.



## -syntax

````
typedef struct D3D12DDI_VIDEO_SCALE_SUPPORT_0022 {
  UINT                                    MaxOutputWidth;
  UINT                                    MaxOutputHeight;
  UINT                                    MinOutputWidth;
  UINT                                    MinOutputHeight;
  D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 ScaleSupportFlags;
} D3D12DDI_VIDEO_SCALE_SUPPORT_0022;
````


## -struct-fields

### -field MaxOutputWidth

The largest output width that can be scaled to.  The largest value allowed is <b>D3D12_REQ_TEXTURE2D_U_OR_V_DIMENSION</b>, which is 16384.


### -field MaxOutputHeight

The largest output height that can be scaled to.  The largest value allowed is <b>D3D12_REQ_TEXTURE2D_U_OR_V_DIMENSION</b>, which is 16384.


### -field MinOutputWidth

The smallest output width that can be scaled to.  The smallest allowed value is 1.


### -field MinOutputHeight

The smallest output height that can be scaled to.  The smallest allowed value is 1.


### -field ScaleSupportFlags

Flags that indicated level of scale support. For more information, see the <a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_scale_support_flags_0022.md">D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS</a> enumeration. 


## -remarks
By default, supported indicates that all possible output size combinations that exist between the maximum  size and minimum size for the extent, inclusive, are supported.  The values in the <i>ScaleSupportFlags</i> value may add additional restrictions.


When scaling is not supported, the maximum and maximum sizes should both be set to the input size and no flags specified.



## -see-also
<dl>
<dt>
<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_scale_support_flags_0022.md">D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_VIDEO_SCALE_SUPPORT_0022 structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

