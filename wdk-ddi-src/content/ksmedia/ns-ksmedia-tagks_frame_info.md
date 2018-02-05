---
UID : NS:ksmedia.tagKS_FRAME_INFO
title : tagKS_FRAME_INFO
author : windows-driver-content
description : The KS_FRAME_INFO structure extends the KSSTREAM_HEADER structure for video streams.
old-location : stream\ks_frame_info.htm
old-project : stream
ms.assetid : 7c2ebe5d-ecb0-41d2-a1bb-7e131ea350a7
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : PKS_FRAME_INFO structure pointer [Streaming Media Devices], ksmedia/PKS_FRAME_INFO, tagKS_FRAME_INFO, stream.ks_frame_info, KS_FRAME_INFO structure [Streaming Media Devices], ksmedia/KS_FRAME_INFO, *PKS_FRAME_INFO, KS_FRAME_INFO, vidcapstruct_1ce3f0b4-3032-4956-83a3-2a92039eb7a0.xml, PKS_FRAME_INFO
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ksmedia.h
req.include-header : Ksmedia.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PKS_FRAME_INFO, KS_FRAME_INFO"
---

# tagKS_FRAME_INFO structure
The <b>KS_FRAME_INFO</b> structure extends the <a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a> structure for video streams.

## Syntax
````
typedef struct tagKS_FRAME_INFO {
  ULONG    ExtendedHeaderSize;
  DWORD    dwFrameFlags;
  LONGLONG PictureNumber;
  LONGLONG DropCount;
  HANDLE   hDirectDraw;
  HANDLE   hSurfaceHandle;
  RECT     DirectDrawRect;
  union {
    LONG  lSurfacePitch;
    DWORD Reserved1;
  };
  DWORD    Reserved2;
  union {
    struct {
      DWORD Reserved3;
      DWORD Reserved4;
    };
    ULONGLONG FrameCompletionNumber;
  };
} KS_FRAME_INFO, *PKS_FRAME_INFO;
````

## Members


`DirectDrawRect`

Specifies the portion of the DirectDraw surface that has been locked. This is normally the entire surface.

`DropCount`

Specifies the number of pictures that were not captured. During capture, the minidriver sets this member. This counter should be incremented whenever a frame should have been captured but was not; this condition usually arises when no buffers were available during capture. Initialize or update this value on transition into KSSTATE_ACQUIRE.

`dwFrameFlags`

Specifies flags indicating additional information about the frame captured. During capture, the minidriver sets this member to one of the following values that are defined in <i>ksmedia.h</i>:
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
KS_VIDEO_FLAG_FRAME

</td>
<td>
Indicates a complete frame.

</td>
</tr>
<tr>
<td>
KS_VIDEO_FLAG_FIELD1

</td>
<td>
Indicates Field 1 of a two-field sequence.

</td>
</tr>
<tr>
<td>
KS_VIDEO_FLAG_FIELD2

</td>
<td>
Indicates Field 2 of a two-field sequence.

</td>
</tr>
<tr>
<td>
KS_VIDEO_FLAG_I_FRAME

</td>
<td>
Indicates that this frame can be completely decoded without reference to any other frames.

</td>
</tr>
<tr>
<td>
KS_VIDEO_FLAG_P_FRAME

</td>
<td>
Indicates that this is a predicted frame.

</td>
</tr>
<tr>
<td>
KS_VIDEO_FLAG_B_FRAME

</td>
<td>
Indicates that this is a bidirectional frame.

</td>
</tr>
</table>

`ExtendedHeaderSize`

Specifies the size of this structure, in bytes.

`hDirectDraw`

Specifies the user-mode handle to DirectDraw. This handle is only provided to the minidriver when capturing to a DirectDraw surface for preview or overlay purposes.

`hSurfaceHandle`

Specifies the user-mode handle to the DirectDraw surface. This handle is only provided to the minidriver when capturing to a DirectDraw surface for preview or overlay purposes.

`PictureNumber`

Specifies a count representing the current picture number. Initialize or update this value on transition into KSSTATE_ACQUIRE.

`Reserved2`

Reserved and should not be used by the minidriver.

## Remarks
The KS_FRAME_INFO structure provides a way to return information about the frame captured, as well as a way to pass Microsoft DirectDraw handles used when capturing to a DirectDraw surface.

The <b>PictureNumber</b> member count represents the count of the current picture, which is calculated in one of two ways depending on the device:
<ul>
<li>
Measure the time since the stream was started and divide by the frame duration. This method is appropriate for devices that do not provide their own clock. For example: 

<pre class="syntax" xml:space="preserve"><code>PictureNumber = ElapsedTime / FrameDuration;</code></pre>
</li>
<li>
Add together the count of frames captured and the count of frame dropped. This method is appropriate for devices that provide their own clock. For example: 

<pre class="syntax" xml:space="preserve"><code>PictureNumber = FramesCaptured + FramesDropped;</code></pre>
</li>
</ul>When calculating <b>PictureNumber</b> and <b>DropCount</b>, it is important to use the frame duration specified when the stream was opened, which may not necessarily match the rate at which the device is actually producing images. For example, a USB camera may only produce images at 7.5 fps, but a client could open the stream at 8 fps. In this case, all calculations should use the 8 fps number. 

For more information about updating <b>PictureNumber</b> and <b>DropCount</b> see <a href="https://msdn.microsoft.com/0adea8fe-1669-4daf-a858-05e014f00a72">Capturing Video</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ksmedia.h (include Ksmedia.h) |

## See Also

<a href="..\ks\ns-ks-ksstream_header.md">KSSTREAM_HEADER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KS_FRAME_INFO structure%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>