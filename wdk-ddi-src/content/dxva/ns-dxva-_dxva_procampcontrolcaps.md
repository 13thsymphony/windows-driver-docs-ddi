---
UID: NS.DXVA._DXVA_PROCAMPCONTROLCAPS
title: _DXVA_ProcAmpControlCaps
author: windows-driver-content
description: The DXVA_ProcAmpControlCaps structure identifies the ProcAmp operations that the hardware supports.
old-location: display\dxva_procampcontrolcaps.htm
old-project: display
ms.assetid: 93de54dc-8826-4b1c-acf7-1861f337318a
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXVA_ProcAmpControlCaps, *LPDXVA_ProcAmpControlCaps, LPDXVA_ProcAmpControlCaps, DXVA_ProcAmpControlCaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: DirectX 9.0 and later versions only.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_ProcAmpControlCaps
req.alt-loc: dxva.h
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
---

# _DXVA_ProcAmpControlCaps structure



## -description
The DXVA_ProcAmpControlCaps structure identifies the ProcAmp operations that the hardware supports.



## -syntax

````
typedef struct _DXVA_ProcAmpControlCaps {
  DWORD     Size;
  DWORD     InputPool;
  D3DFORMAT d3dOutputFormat;
  DWORD     ProcAmpControlProps;
  DWORD     VideoProcessingCaps;
} DXVA_ProcAmpControlCaps, *LPDXVA_ProcAmpControlCaps;
````


## -struct-fields

### -field Size

Specifies the size of this structure in bytes.


### -field InputPool

Indicates the memory pool from which the ProcAmp control source surfaces should be allocated. For more information, see the D3DPOOL enumeration in the Microsoft Window SDK documentation.


### -field d3dOutputFormat

Indicates the Direct3D surface format of the output frames. Usually the ProcAmp device outputs frames in a surface format that matches the input surface format. This member ensures that the <a href="wdkgloss.v#wdkgloss.video_mixer_renderer__vmr_#wdkgloss.video_mixer_renderer__vmr_"><i>VMR</i></a> or other video renderer is able to supply the correct format for the output frame surfaces to the ProcAmp control hardware. If the <b>DXVA_VideoProcess_YUV2RGB</b> flag is returned in the <a href="display.dxva_videoprocesscaps">DXVA_VideoProcessCaps</a> structure, the VMR assumes that valid output formats are specified by this member as well as the RGB32 format.


### -field ProcAmpControlProps

Identifies the ProcAmp operations that the hardware supports. The driver should return a logical combination of the following ProcAmp operations.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>DXVA_ProcAmp_None</b>

</td>
<td>
No operations are allowed.

</td>
</tr>
<tr>
<td>
<b>DXVA_ProcAmp_Brightness</b>

</td>
<td>
Brightness adjustments to the video image are allowed.

</td>
</tr>
<tr>
<td>
<b>DXVA_ProcAmp_Contrast</b>

</td>
<td>
Contrast adjustments to the video image are allowed.

</td>
</tr>
<tr>
<td>
<b>DXVA_ProcAmp_Hue</b>

</td>
<td>
Hue adjustments to the video image are allowed.

</td>
</tr>
<tr>
<td>
<b>DXVA_ProcAmp_Saturation</b>

</td>
<td>
Saturation adjustments to the video image are allowed.

</td>
</tr>
</table>
 


### -field VideoProcessingCaps

Identifies the operations that can be performed by the ProcAmp control hardware concurrently with the requested ProcAmp adjustment. The driver should return a logical combination of one of the following ProcAmp operations.

<table>
<tr>
<th>Value</th>
<th>Description</th>
</tr>
<tr>
<td>
<b>DXVA_VideoProcess_None</b>

</td>
<td>
No operations are allowed.

</td>
</tr>
<tr>
<td>
<b>DXVA_VideoProcess_YUV2RGB</b>

</td>
<td>
Video conversion from the YUV color space to the RGB color space is allowed. The RGB format used will have at least 8 bits of precision for each color component. If this is possible, a buffer copy within the VMR can be avoided. Note that there is no requirement to convert from the RGB color space to the YUV color space. 

</td>
</tr>
<tr>
<td>
<b>DXVA_VideoProcess_StretchX</b>

</td>
<td>
Aspect ratio correction can be performed at the same time as the video is being ProcAmp-adjusted if the hardware is able to stretch or shrink horizontally.

</td>
</tr>
<tr>
<td>
<b>DXVA_VideoProcess_StretchY</b>

</td>
<td>
Aspect ratio adjustment is combined with a general picture resizing operation to scale the video image within an application-defined composition space. This is rare and not an essential feature. It is best if the scaling needed for resizing the video to fit into the application window can be done at the same time as the scaling needed for ProcAmp adjustment. This avoids cumulative artifacts.

</td>
</tr>
<tr>
<td>
<b>DXVA_VideoProcess_AlphaBlend</b>

</td>
<td>
Indicates that the VMR will not perform a buffer copy when an alpha value is changed. It is rare that applications alter the constant alpha value associated with the video stream, so this is a low priority feature.

</td>
</tr>
</table>
 


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
DirectX 9.0 and later versions only.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dxva.h (include Dxva.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxva_videoprocesscaps">DXVA_VideoProcessCaps</a>
</dt>
<dt>
<a href="display.dxva_procampcontrolprop">DXVA_ProcAmpControlProp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_ProcAmpControlCaps structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

