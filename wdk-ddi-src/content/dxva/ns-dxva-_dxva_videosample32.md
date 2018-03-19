---
UID: NS:dxva._DXVA_VideoSample32
title: "_DXVA_VideoSample32"
author: windows-driver-content
description: The DXVA_VideoSample32 structure is used for forwarding 32-bit DXVA_DeinterlaceBltEx calls on 64-bit drivers.
old-location: display\dxva_videosample32.htm
old-project: display
ms.assetid: 78609b64-38fa-4431-bc74-8a83fe687a45
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXVA_VideoSample32, DXVA_VideoSample32 structure [Display Devices], _DXVA_VideoSample32, display.dxva_videosample32, dxva/DXVA_VideoSample32, dxvaref_3e581191-6878-4daa-87e6-62188fa4708e.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.Only compiles for a 64-bit version of the operating system.
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	dxva.h
api_name:
-	DXVA_VideoSample32
product: Windows
targetos: Windows
req.typenames: DXVA_VideoSample32
---

# _DXVA_VideoSample32 structure
The DXVA_VideoSample32 structure is used for forwarding  32-bit <a href="..\dxva\ns-dxva-_dxva_deinterlacebltex.md">DXVA_DeinterlaceBltEx</a> calls on 64-bit drivers.

## Syntax
````
typedef struct _DXVA_VideoSample32 {
  REFERENCE_TIME   rtStart;
  REFERENCE_TIME   rtEnd;
  DWORD            SampleFormat;
  DWORD            SampleFlags;
  DWORD            lpDDSSrcSurface;
  RECT             rcSrc;
  RECT             rcDst;
  DXVA_AYUVsample2 Palette[16];
} DXVA_VideoSample32;
````

## Members


`rtStart`

Specifies the start time of the sample.

`rtEnd`

Specifies the end time of the sample.

`SampleFormat`

Specifies the format of the sample as defined by values of the <a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a> enumeration type.

`SampleFlags`

Specifies a collection of flags that indicate changes in the current sample frame from the previous sample frame. This member is a bitwise-OR of one or more of the flags in the <a href="..\dxva\ne-dxva-_dxva_sampleflags.md">DXVA_SampleFlags</a> enumeration type.

`lpDDSSrcSurface`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a> structure that represents the sample.

`rcSrc`

Specifies a <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that describes the upper-left and lower-right points of a rectangle on the source surface. These points define the area of the source data for the bit-block transfer and its position on the source surface.

`rcDst`

Specifies a RECT structure that describes the upper-left and lower-right points of a rectangle on the destination surface. These points define the area in which the bit-block transfer should occur and its position on the destination surface.

`Palette`

Specifies an array of <a href="..\dxva\ns-dxva-_dxva_ayuvsample2.md">DXVA_AYUVsample2</a> structures that represent a complete 16-color palette for palletized video substream pixel formats. The driver uses this palette to composite the substream sample. For nonpalletized pixel formats, the palette is zero and can be ignored.

## Remarks
The compiler adds 4 bytes of padding to align the structure to 8 bytes.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.Only compiles for a 64-bit version of the operating system. This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.Only compiles for a 64-bit version of the operating system. |
| **Header** | dxva.h (include Dxva.h) |

## See Also

<a href="..\dxva\ns-dxva-_dxva_ayuvsample2.md">DXVA_AYUVsample2</a>



<a href="..\dxva\ns-dxva-_dxva_extendedformat.md">DXVA_ExtendedFormat</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551733">DD_SURFACE_LOCAL</a>



<a href="..\dxva\ne-dxva-_dxva_sampleformat.md">DXVA_SampleFormat</a>



<a href="..\dxva\ns-dxva-_dxva_deinterlacebltex.md">DXVA_DeinterlaceBltEx</a>



<a href="..\dxva\ne-dxva-_dxva_sampleflags.md">DXVA_SampleFlags</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>