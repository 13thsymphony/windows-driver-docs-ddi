---
UID: NS.VIDEO._VIDEO_CHILD_STATE
title: _VIDEO_CHILD_STATE
author: windows-driver-content
description: The VIDEO_CHILD_STATE structure contains information about a child device and the state into which it should be placed.
old-location: display\video_child_state.htm
old-project: display
ms.assetid: 69a2eebb-9294-4fc1-871a-587792f84f35
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _VIDEO_CHILD_STATE, VIDEO_CHILD_STATE, *PVIDEO_CHILD_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_CHILD_STATE
req.alt-loc: video.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: See Remarks section.
req.product: Windows 10 or later.
---

# _VIDEO_CHILD_STATE structure



## -description
The VIDEO_CHILD_STATE structure contains information about a child device and the state into which it should be placed.


## -syntax

````
typedef struct _VIDEO_CHILD_STATE {
  ULONG Id;
  ULONG State;
} VIDEO_CHILD_STATE, *PVIDEO_CHILD_STATE;
````


## -struct-fields

### -field Id

Specifies the ID for a particular child device, as given to it by the miniport driver. This value is the same as that returned in the <i>UId</i> parameter of the <a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a> function.

### -field State

Specifies the new state, on or off, for the child device. A value of one (1) indicates that the child device should be turned on; a value of zero (0) indicates that it should be turned off. One possible use for <b>State</b> is in hotkey switching from one display device to another.

## -remarks
One member of the <a href="display.video_child_state_configuration">VIDEO_CHILD_STATE_CONFIGURATION</a> structure is an array of VIDEO_CHILD_STATE structures. Each of these structures maintains state information for one of an adapter's child devices.

## -requirements
<table>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Video.h (include Video.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.video_child_state_configuration">VIDEO_CHILD_STATE_CONFIGURATION</a>
</dt>
<dt>
<a href="..\video\nc-video-pvideo_hw_get_child_descriptor.md">HwVidGetVideoChildDescriptor</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_CHILD_STATE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
