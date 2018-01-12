---
UID: NS:video._VIDEO_CHILD_STATE_CONFIGURATION
title: _VIDEO_CHILD_STATE_CONFIGURATION
author: windows-driver-content
description: The VIDEO_CHILD_STATE_CONFIGURATION structure contains an array of VIDEO_CHILD_STATE structures, each holding the state of a particular child device.
old-location: display\video_child_state_configuration.htm
old-project: display
ms.assetid: e298ef49-d285-426a-9028-78f7f54340b2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _VIDEO_CHILD_STATE_CONFIGURATION, *PVIDEO_CHILD_STATE_CONFIGURATION, VIDEO_CHILD_STATE_CONFIGURATION
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
req.alt-api: VIDEO_CHILD_STATE_CONFIGURATION
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
req.typenames: *PVIDEO_CHILD_STATE_CONFIGURATION, VIDEO_CHILD_STATE_CONFIGURATION
req.product: Windows 10 or later.
---

# _VIDEO_CHILD_STATE_CONFIGURATION structure



## -description
The VIDEO_CHILD_STATE_CONFIGURATION structure contains an array of <a href="..\video\ns-video-_video_child_state.md">VIDEO_CHILD_STATE</a> structures, each holding the state of a particular child device.



## -syntax

````
typedef struct _VIDEO_CHILD_STATE_CONFIGURATION {
  ULONG             Count;
  VIDEO_CHILD_STATE ChildStateArray[ANYSIZE_ARRAY];
} VIDEO_CHILD_STATE_CONFIGURATION, *PVIDEO_CHILD_STATE_CONFIGURATION;
````


## -struct-fields

### -field Count

Specifies the number of structures in the <b>ChildStateArray</b> member.


### -field ChildStateArray

Is an array of <a href="..\video\ns-video-_video_child_state.md">VIDEO_CHILD_STATE</a> structures. Each element of this array contains the ID and state for a particular child device.


## -remarks
The video port driver sends a VIDEO_CHILD_STATE_CONFIGURATION structure to the miniport driver for the following IOCTLs:


<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_validate_child_state_configuration.md">IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION</a>, in which the video port driver queries the miniport driver to determine whether the specified state for each child device in <b>ChildStateArray</b> is valid.


<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_child_state_configuration.md">IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION</a>, in which the video port driver requests the miniport driver to make the specified state change for each child device in <b>ChildStateArray</b>.


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
<a href="..\video\ns-video-_video_child_state.md">VIDEO_CHILD_STATE</a>
</dt>
<dt>
<a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>
</dt>
<dt>
<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_validate_child_state_configuration.md">IOCTL_VIDEO_VALIDATE_CHILD_STATE_CONFIGURATION</a>
</dt>
<dt>
<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_set_child_state_configuration.md">IOCTL_VIDEO_SET_CHILD_STATE_CONFIGURATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_CHILD_STATE_CONFIGURATION structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

