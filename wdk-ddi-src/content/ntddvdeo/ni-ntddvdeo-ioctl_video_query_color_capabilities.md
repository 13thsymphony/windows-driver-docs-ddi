---
UID: NI.ntddvdeo.IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
title: IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
author: windows-driver-content
description: Returns the color-capabilities information found in the VDDP description file for the adapter.
old-location: display\ioctl_video_query_color_capabilities.htm
old-project: display
ms.assetid: ba1a1fcd-9551-41cb-b1f9-097b51a26380
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES
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

# IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES IOCTL



## -description

Returns the color-capabilities information found in the VDDP description file for the adapter. Support for this nonmodal request is optional. However, if a miniport driver supports this request, it cannot return a subset of the color-capabilities information.

Returns the color-capabilities information found in the VDDP description file for the adapter. Support for this nonmodal request is optional. However, if a miniport driver supports this request, it cannot return a subset of the color-capabilities information.


## -ioctlparameters

### -input-buffer
None

### -input-buffer-length

<text></text>

### -output-buffer
The miniport driver returns all VIDEO_COLOR_CAPABILITIES information in the VRP <b>OutputBuffer</b>.

### -output-buffer-length

<text></text>

### -in-out-buffer

<text></text>

### -inout-buffer-length

<text></text>

### -status-block
I/O Status block
If the miniport driver successfully returns the color-capabilities data, it sets the <b>Information</b> member of the <a href="display.status_block">STATUS_BLOCK</a> structure to <b>sizeof</b>(VIDEO_COLOR_CAPABILITIES); otherwise, the miniport driver sets this member to zero.

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
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20IOCTL_VIDEO_QUERY_COLOR_CAPABILITIES control code%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
