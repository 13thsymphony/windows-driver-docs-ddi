---
UID : NE:dxva._DXVA_SampleFormat
title : _DXVA_SampleFormat
author : windows-driver-content
description : The DXVA_SampleFormat enumeration type describes the format of data that the input sample contains.
old-location : display\dxva_sampleformat.htm
old-project : display
ms.assetid : 90cec61b-fe49-4fc7-b666-e74f745a00b1
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _DXVA_SampleFormat, DXVA_SampleFormat
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : dxva.h
req.include-header : Dxva.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : DXVA_SampleFormat
req.alt-loc : dxva.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : DXVA_SampleFormat
---

# _DXVA_SampleFormat Enumeration
The DXVA_SampleFormat enumeration type describes the format of data that the input sample contains.

## Syntax
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

## Constants

<table>

<tr>
<td>DXVA_SampleFieldInterleavedEvenFirst</td>
<td>Specifies that the sample contains two interleaved fields; the even field is temporally first.</td>
</tr>

<tr>
<td>DXVA_SampleFieldInterleavedOddFirst</td>
<td>Specifies that the sample contains two interleaved fields; the odd field is temporally first.</td>
</tr>

<tr>
<td>DXVA_SampleFieldSingleEven</td>
<td>Specifies that the sample contains an even interleaved field.</td>
</tr>

<tr>
<td>DXVA_SampleFieldSingleOdd</td>
<td>Specifies that the sample contains an odd interleaved field.</td>
</tr>

<tr>
<td>DXVA_SampleFormatMask</td>
<td>Specifies the sample format mask. The first 8 (0x000000FF) bits of a DWORD can be used to specify input sample format.</td>
</tr>

<tr>
<td>DXVA_SamplePreviousFrame</td>
<td>Specifies that the sample contains the previous output frame.</td>
</tr>

<tr>
<td>DXVA_SampleProgressiveFrame</td>
<td>Specifies that the sample contains a progressive frame.</td>
</tr>

<tr>
<td>DXVA_SampleSubStream</td>
<td>Windows Server 2003 SP1 and later and Windows XP SP2 and later versions only.

Specifies that the sample contains a video substream.</td>
</tr>

<tr>
<td>DXVA_SampleUnknown</td>
<td>Specifies that the sample format is unknown.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<dl>
<dt>
<a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a>
</dt>
<dt>
<a href="..\dxva\ns-dxva-_dxva_videosample.md">DXVA_VideoSample</a>
</dt>
<dt>
<a href="..\dxva\ns-dxva-_dxva_videosample2.md">DXVA_VideoSample2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_SampleFormat enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>