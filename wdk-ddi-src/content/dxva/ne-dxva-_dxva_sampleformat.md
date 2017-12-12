---
UID: NE.dxva._DXVA_SampleFormat
title: _DXVA_SampleFormat
author: windows-driver-content
description: The DXVA_SampleFormat enumeration type describes the format of data that the input sample contains.
old-location: display\dxva_sampleformat.htm
old-project: display
ms.assetid: 90cec61b-fe49-4fc7-b666-e74f745a00b1
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVA_SampleFormat, DXVA_SampleFormat
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_SampleFormat
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

# _DXVA_SampleFormat enumeration



## -description
The DXVA_SampleFormat enumeration type describes the format of data that the input sample contains.



## -syntax

````
typedef enum _DXVA_SampleFormat { 
  DXVA_SampleFormatMask                 = 0xFF,
  DXVA_SampleUnknown                    = 0,
  DXVA_SamplePreviousFrame              = 1,
  DXVA_SampleProgressiveFrame           = 2,
  DXVA_SampleFieldInterleavedEvenFirst  = 3,
  DXVA_SampleFieldInterleavedOddFirst   = 4,
  DXVA_SampleFieldSingleEven            = 5,
  DXVA_SampleFieldSingleOdd             = 6,
  DXVA_SampleSubStream                  = 7
} DXVA_SampleFormat;
````


## -enum-fields

### -field DXVA_SampleFormatMask

Specifies the sample format mask. The first 8 (0x000000FF) bits of a DWORD can be used to specify input sample format. 



### -field DXVA_SampleUnknown

Specifies that the sample format is unknown. 



### -field DXVA_SamplePreviousFrame

Specifies that the sample contains the previous output frame.


### -field DXVA_SampleProgressiveFrame

Specifies that the sample contains a progressive frame.


### -field DXVA_SampleFieldInterleavedEvenFirst

Specifies that the sample contains two interleaved fields; the even field is temporally first.


### -field DXVA_SampleFieldInterleavedOddFirst

Specifies that the sample contains two interleaved fields; the odd field is temporally first.


### -field DXVA_SampleFieldSingleEven

Specifies that the sample contains an even interleaved field.


### -field DXVA_SampleFieldSingleOdd

Specifies that the sample contains an odd interleaved field.


### -field DXVA_SampleSubStream

Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.

Specifies that the sample contains a video substream.


## -remarks


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
<a href="display.dxva_extendedformat">DXVA_ExtendedFormat</a>
</dt>
<dt>
<a href="display.dxva_videosample">DXVA_VideoSample</a>
</dt>
<dt>
<a href="display.dxva_videosample2">DXVA_VideoSample2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_SampleFormat enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

