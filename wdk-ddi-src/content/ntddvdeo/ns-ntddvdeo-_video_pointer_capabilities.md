---
UID: NS:ntddvdeo._VIDEO_POINTER_CAPABILITIES
title: "_VIDEO_POINTER_CAPABILITIES"
author: windows-driver-content
description: Contains capabilities of the screen pointer.
old-location: display\video_pointer_capabilities.htm
old-project: display
ms.assetid: bc5f98da-1e2e-421b-9c76-97359e51b526
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: ntddvdeo/VIDEO_POINTER_CAPABILITIES, VIDEO_POINTER_CAPABILITIES, display.video_pointer_capabilities, Video_Structs_03a35602-adfd-4485-a155-866b578fa807.xml, _VIDEO_POINTER_CAPABILITIES, ntddvdeo/PVIDEO_POINTER_CAPABILITIES, PVIDEO_POINTER_CAPABILITIES, VIDEO_POINTER_CAPABILITIES structure [Display Devices], *PVIDEO_POINTER_CAPABILITIES, PVIDEO_POINTER_CAPABILITIES structure pointer [Display Devices]
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
-	Ntddvdeo.h
apiname:
-	VIDEO_POINTER_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_POINTER_CAPABILITIES, VIDEO_POINTER_CAPABILITIES"
---

# _VIDEO_POINTER_CAPABILITIES structure
The <b>VIDEO_POINTER_CAPABILITIES</b> structure contains capabilities of the screen pointer.

## Syntax
````
typedef struct _VIDEO_POINTER_CAPABILITIES {
  ULONG Flags;
  ULONG MaxWidth;
  ULONG MaxHeight;
  ULONG HWPtrBitmapStart;
  ULONG HWPtrBitmapEnd;
} VIDEO_POINTER_CAPABILITIES, *PVIDEO_POINTER_CAPABILITIES;
````

## Members


`Flags`

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

`HWPtrBitmapEnd`

Specifies the last offset, in CPU-addressable units, in the memory bitmap that is used to store the hardware pointer bitmap. A value of –1 is not valid.

`HWPtrBitmapStart`

Specifies the first offset, in CPU-addressable units, in the memory bitmap that is used to store the hardware pointer bitmap. A value of –1 is not valid.

`MaxHeight`

Specifies the maximum height of the pointer, in pixels.

`MaxWidth`

Specifies the maximum width of the pointer, in pixels.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddvdeo.h (include Ntddvdeo.h) |