---
UID: NE.d3dukmdt._D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING
title: _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING
author: windows-driver-content
description: The D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration is used to indicate the scan line ordering of a video output signal.
old-location: display\d3dddi_video_signal_scanline_ordering.htm
old-project: display
ms.assetid: f0dcfd93-1706-41f7-aab5-f9e9dd58e9b3
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING, D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING
req.alt-loc: d3dukmdt.h
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

# _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration



## -description
The D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration is used to indicate the scan line ordering of a video output signal.  



## -syntax

````
typedef enum _D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING { 
  D3DDDI_VSSLO_UNINITIALIZED               = 0,
  D3DDDI_VSSLO_PROGRESSIVE                 = 1,
  D3DDDI_VSSLO_INTERLACED_UPPERFIELDFIRST  = 2,
  D3DDDI_VSSLO_INTERLACED_LOWERFIELDFIRST  = 3,
  D3DDDI_VSSLO_OTHER                       = 255
} D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING;
````


## -enum-fields

### -field D3DDDI_VSSLO_UNINITIALIZED

Indicates that a variable of type D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING has not yet been assigned a meaningful value.


### -field D3DDDI_VSSLO_PROGRESSIVE

Indicates that each field contains an entire frame.


### -field D3DDDI_VSSLO_INTERLACED_UPPERFIELDFIRST

Indicates that each field contains half of a frame, and the odd scan lines are displayed first. 


### -field D3DDDI_VSSLO_INTERLACED_LOWERFIELDFIRST

Indicates that each field contains half of a frame, and the even scan lines are displayed first. 


### -field D3DDDI_VSSLO_OTHER

Indicates that the video signal has a scan line ordering other than those given in the previous constants of this enumeration.


## -remarks
The values of the D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING enumeration type indicate whether the image displayed on the monitor contains the entire content of a video frame or only half of the content (that is, either the even or odd scan lines, which occur interchangeably). The values also indicate which field comes first in the ordering.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dukmdt.h (include D3dukmdt.h)</dt>
</dl>
</td>
</tr>
</table>