---
UID: NS:dxva._DXVA_VideoDesc
title: _DXVA_VideoDesc
author: windows-driver-content
description: The DXVA_VideoDesc structure is sent by the renderer to the driver to specify a description of the video stream on which the deinterlacing or frame-rate conversion operation is to be performed.
old-location: display\dxva_videodesc.htm
old-project: display
ms.assetid: 5623ed85-e78a-48f2-ab21-e6364da86b2a
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVA_VideoDesc, DXVA_VideoDesc, *LPDXVA_VideoDesc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_VideoDesc
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
req.typenames: DXVA_VideoDesc, *LPDXVA_VideoDesc
---

# _DXVA_VideoDesc structure



## -description
The DXVA_VideoDesc structure is sent by the renderer to the driver to specify a description of the video stream on which the deinterlacing or frame-rate conversion operation is to be performed.



## -syntax

````
typedef struct _DXVA_VideoDesc {
  DWORD          Size;
  DWORD          SampleWidth;
  DWORD          SampleHeight;
  DWORD          SampleFormat;
  D3DFORMAT      d3dFormat;
  DXVA_Frequency InputSampleFreq;
  DXVA_Frequency OutputFrameFreq;
} DXVA_VideoDesc, *LPDXVA_VideoDesc;
````


## -struct-fields

### -field Size

Specifies the size of this structure, in bytes.


### -field SampleWidth

Specifies the width of the sample, in pixels.


### -field SampleHeight

Specifies the height of the sample, in pixels.


### -field SampleFormat

Specifies the format of the sample defined by the <a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a> structure.


### -field d3dFormat

Specifies the Direct3D surface format of the sample.


### -field InputSampleFreq

Specifies the frequency of incoming video defined by the <a href="..\dxva\ns-dxva-_dxva_frequency.md">DXVA_Frequency</a> structure.


### -field OutputFrameFreq

Specifies the desired frame rate of output video as defined by <a href="..\dxva\ns-dxva-_dxva_frequency.md">DXVA_Frequency</a>.


## -remarks
For examples showing structure member values for deinterlacing or converting different types of content, see <a href="https://msdn.microsoft.com/be721bde-3c72-4942-9f33-5ea1bf2d187c">DeinterlaceQueryAvailableModes</a>.


## -requirements
<table>
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
<a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a>
</dt>
<dt>
<a href="..\dxva\ns-dxva-_dxva_frequency.md">DXVA_Frequency</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoDesc structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

