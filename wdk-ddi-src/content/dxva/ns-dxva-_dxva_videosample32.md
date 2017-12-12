---
UID: NS.DXVA._DXVA_VIDEOSAMPLE32
title: _DXVA_VideoSample32
author: windows-driver-content
description: The DXVA_VideoSample32 structure is used for forwarding 32-bit DXVA_DeinterlaceBltEx calls on 64-bit drivers.
old-location: display\dxva_videosample32.htm
old-project: display
ms.assetid: 78609b64-38fa-4431-bc74-8a83fe687a45
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVA_VideoSample32, DXVA_VideoSample32
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
req.alt-api: DXVA_VideoSample32
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

# _DXVA_VideoSample32 structure



## -description
The DXVA_VideoSample32 structure is used for forwarding  32-bit <a href="display.dxva_deinterlacebltex">DXVA_DeinterlaceBltEx</a> calls on 64-bit drivers.



## -syntax

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


## -struct-fields

### -field rtStart

Specifies the start time of the sample.


### -field rtEnd

Specifies the end time of the sample.


### -field SampleFormat

Specifies the format of the sample as defined by values of the <a href="display.dxva_extendedformat">DXVA_ExtendedFormat</a> enumeration type. 


### -field SampleFlags

Specifies a collection of flags that indicate changes in the current sample frame from the previous sample frame. This member is a bitwise-OR of one or more of the flags in the <a href="display.dxva_sampleflags">DXVA_SampleFlags</a> enumeration type.


### -field lpDDSSrcSurface

Pointer to a <a href="display.dd_surface_local">DD_SURFACE_LOCAL</a> structure that represents the sample.


### -field rcSrc

Specifies a <a href="display.rect">RECT</a> structure that describes the upper-left and lower-right points of a rectangle on the source surface. These points define the area of the source data for the bit-block transfer and its position on the source surface.


### -field rcDst

Specifies a RECT structure that describes the upper-left and lower-right points of a rectangle on the destination surface. These points define the area in which the bit-block transfer should occur and its position on the destination surface.


### -field Palette

Specifies an array of <a href="display.dxva_ayuvsample2">DXVA_AYUVsample2</a> structures that represent a complete 16-color palette for palletized video substream pixel formats. The driver uses this palette to composite the substream sample. For nonpalletized pixel formats, the palette is zero and can be ignored.


## -remarks
The compiler adds 4 bytes of padding to align the structure to 8 bytes.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.Only compiles for a 64-bit version of the operating system.

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
<a href="display.dxva_ayuvsample2">DXVA_AYUVsample2</a>
</dt>
<dt>
<a href="display.dxva_deinterlacebltex">DXVA_DeinterlaceBltEx</a>
</dt>
<dt>
<a href="display.dxva_extendedformat">DXVA_ExtendedFormat</a>
</dt>
<dt>
<a href="display.dxva_sampleflags">DXVA_SampleFlags</a>
</dt>
<dt>
<a href="display.dxva_sampleformat">DXVA_SampleFormat</a>
</dt>
<dt>
<a href="display.dd_surface_local">DD_SURFACE_LOCAL</a>
</dt>
<dt>
<a href="display.rect">RECT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_VideoSample32 structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

