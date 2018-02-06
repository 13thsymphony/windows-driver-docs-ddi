---
UID: NS:dxva._DXVA_DeinterlaceBlt
title: "_DXVA_DeinterlaceBlt"
author: windows-driver-content
description: The DXVA_DeinterlaceBlt structure is sent by the VMR to the accelerator to specify the deinterlace or frame-rate conversion parameters for bit-block transfers.
old-location: display\dxva_deinterlaceblt.htm
old-project: display
ms.assetid: 0512a825-9cec-4ca0-9686-df5b3d2b216b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: dxva/DXVA_DeinterlaceBlt, dxvaref_69a3b788-495c-42a0-acae-8d8242d963c6.xml, DXVA_DeinterlaceBlt, _DXVA_DeinterlaceBlt, DXVA_DeinterlaceBlt structure [Display Devices], display.dxva_deinterlaceblt
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
-	dxva.h
apiname:
-	DXVA_DeinterlaceBlt
product: Windows
targetos: Windows
req.typenames: DXVA_DeinterlaceBlt
---

# _DXVA_DeinterlaceBlt structure
The DXVA_DeinterlaceBlt structure is sent by the VMR to the accelerator to specify the deinterlace or frame-rate conversion parameters for bit-block transfers.

## Syntax
````
typedef struct _DXVA_DeinterlaceBlt {
  DWORD            Size;
  DWORD            Reserved;
  REFERENCE_TIME   rtTarget;
  RECT             DstRect;
  RECT             SrcRect;
  DWORD            NumSourceSurfaces;
  FLOAT            Alpha;
  DXVA_VideoSample Source[MAX_DEINTERLACE_SURFACES];
} DXVA_DeinterlaceBlt;
````

## Members


`Alpha`

Specifies the transparency of the output image as it is written to the destination surface. A value of  0.0F indicates transparent. A value of 1.0F indicates opaque.

`DstRect`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the upper left and lower right points of a rectangle on the destination surface. These points define the area in which the bit-block transfer should occur and its position on the destination surface.

`NumSourceSurfaces`

Specifies the number of valid surfaces passed in the <b>Source</b> array.

`Reserved`



`rtTarget`

Identifies the location of the output frame within the sequence of input frames. If only deinterlacing is performed, the target time should coincide with either the starting display time of a reference sample, as defined in the <a href="..\dxva\ns-dxva-_dxva_videosample.md">DXVA_VideoSample</a> structure, or the midpoint between the starting display time and the ending display time. For more information, see Remarks.

If a frame rate conversion is requested, the <b>rtTarget</b> time can be different from any of the <b>rtStart</b> times of the reference samples.

`Size`

Specifies the size of this structure in bytes.

`Source`

An array of <a href="..\dxva\ns-dxva-_dxva_videosample.md">DXVA_VideoSample</a> structures that specify the reference input samples needed for this deinterlacing or frame-rate conversion operation.

`SrcRect`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the upper left and lower right points of a rectangle on the source surface. These points define the area of the source data for the bit-block transfer and its position on the source surface.

## Remarks
When creating a single frame from one field in a sample, as defined in the <a href="..\dxva\ns-dxva-_dxva_videosample.md">DXVA_VideoSample</a> structure, <b>rtTarget</b> should be the starting display time for that field. If you have two fields in one sample and want to deinterlace both, <a href="https://msdn.microsoft.com/0aa68d0c-8c2b-41fe-9e46-a41b157fbd98">DeinterlaceBlt</a> will be called twice. The first time <i>DeinterlaceBlt</i> is called, <b>rtTarget</b> will be the starting display time. The second time <i>DeinterlaceBlt</i> is called, <b>rtTarget</b> will be the midpoint between the starting display time and the ending display time. In other words, for the first call, <b>rtTarget</b> = <b>rtStart</b>. For the second call, <b>rtTarget</b> = (<b>rtStart</b> + <b>rtEnd</b>) / 2.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<a href="..\dxva\ns-dxva-_dxva_videosample.md">DXVA_VideoSample</a>

<a href="..\dxva\ns-dxva-_dxva_deinterlacecaps.md">DXVA_DeinterlaceCaps</a>

<a href="https://msdn.microsoft.com/0aa68d0c-8c2b-41fe-9e46-a41b157fbd98">DeinterlaceBlt</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_DeinterlaceBlt structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>