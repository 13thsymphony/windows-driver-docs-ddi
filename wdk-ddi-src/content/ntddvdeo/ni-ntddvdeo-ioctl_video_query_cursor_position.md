---
UID: NI.ntddvdeo.IOCTL_VIDEO_QUERY_CURSOR_POSITION
title: IOCTL_VIDEO_QUERY_CURSOR_POSITION
author: windows-driver-content
description: Returns the current cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.
old-location: display\ioctl_video_query_cursor_position.htm
old-project: display
ms.assetid: 0ca9aa92-7b9f-4fd4-a41e-663ac1aa5799
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _TAPE_WRITE_MARKS, *PTAPE_WRITE_MARKS, TAPE_WRITE_MARKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: ntddvdeo.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IOCTL_VIDEO_QUERY_CURSOR_POSITION
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

# IOCTL_VIDEO_QUERY_CURSOR_POSITION IOCTL



## -description

Returns the current cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.



Returns the current cursor position (row and column). Miniport drivers for VGA-compatible adapters are required to support this modal request; optional for other miniport drivers.



## -ioctlparameters

### -input-buffer
None


### -input-buffer-length

<text></text>

### -output-buffer
The miniport driver returns a VIDEO_CURSOR_POSITION structure in the VRP <b>OutputBuffer</b>.


### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the miniport driver successfully returns the cursor position, it sets the <b>Information</b> member of the <a href="display.status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_CURSOR_POSITION); otherwise, the miniport driver sets this member to zero.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.status_block">STATUS_BLOCK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_QUERY_CURSOR_POSITION control code%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

