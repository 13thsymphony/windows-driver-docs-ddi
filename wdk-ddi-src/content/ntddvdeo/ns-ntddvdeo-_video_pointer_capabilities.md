---
UID: NS.NTDDVDEO._VIDEO_POINTER_CAPABILITIES
title: _VIDEO_POINTER_CAPABILITIES
author: windows-driver-content
description: Contains capabilities of the screen pointer.
old-location: display\video_pointer_capabilities.htm
old-project: display
ms.assetid: bc5f98da-1e2e-421b-9c76-97359e51b526
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _VIDEO_POINTER_CAPABILITIES, VIDEO_POINTER_CAPABILITIES, *PVIDEO_POINTER_CAPABILITIES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddvdeo.h
req.include-header: Ntddvdeo.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_POINTER_CAPABILITIES
req.alt-loc: Ntddvdeo.h
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

# _VIDEO_POINTER_CAPABILITIES structure



## -description
The <b>VIDEO_POINTER_CAPABILITIES</b> structure contains capabilities of the screen pointer.


## -syntax

````
typedef struct _VIDEO_POINTER_CAPABILITIES {
  ULONG Flags;
  ULONG MaxWidth;
  ULONG MaxHeight;
  ULONG HWPtrBitmapStart;
  ULONG HWPtrBitmapEnd;
} VIDEO_POINTER_CAPABILITIES, *PVIDEO_POINTER_CAPABILITIES;
````


## -struct-fields

### -field Flags

A set of flags that specify certain capabilities of the pointer. Flags can be a combination of the following values.
<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
VIDEO_MODE_ASYNC_POINTER
</td>
<td>
The pointer can be updated asynchronously to drawing operations.
</td>
</tr>
<tr>
<td>
VIDEO_MODE_MONO_POINTER
</td>
<td>
A monochrome hardware pointer is supported.
</td>
</tr>
<tr>
<td>
VIDEO_MODE_COLOR_POINTER
</td>
<td>
A color hardware pointer is supported.
</td>
</tr>
<tr>
<td>
VIDEO_MODE_ANIMATE_START
</td>
<td>
The current pointer has the same hotspot as the previous pointer.
</td>
</tr>
<tr>
<td>
VIDEO_MODE_ANIMATE_UPDATE
</td>
<td>
The current pointer has the same hotspot as the previous pointer.
</td>
</tr>
</table>
 

### -field MaxWidth

Specifies the maximum width of the pointer, in pixels.

### -field MaxHeight

Specifies the maximum height of the pointer, in pixels.

### -field HWPtrBitmapStart

Specifies the first offset, in CPU-addressable units, in the memory bitmap that is used to store the hardware pointer bitmap. A value of –1 is not valid.

### -field HWPtrBitmapEnd

Specifies the last offset, in CPU-addressable units, in the memory bitmap that is used to store the hardware pointer bitmap. A value of –1 is not valid.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h (include Ntddvdeo.h)</dt>
</dl>
</td>
</tr>
</table>