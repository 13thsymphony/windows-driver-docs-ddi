---
UID: NS.NTDDVDEO._VIDEO_NUM_MODES
title: _VIDEO_NUM_MODES
author: windows-driver-content
description: The VIDEO_NUM_MODES structure contains the number of modes supported by a video adapter, and the size of the structure that describes each mode.
old-location: display\video_num_modes.htm
old-project: display
ms.assetid: d4ca1276-c0f6-46c6-bf86-3cd2a0c5f194
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _VIDEO_NUM_MODES, *PVIDEO_NUM_MODES, VIDEO_NUM_MODES
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
req.alt-api: VIDEO_NUM_MODES
req.alt-loc: ntddvdeo.h
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

# _VIDEO_NUM_MODES structure



## -description
The VIDEO_NUM_MODES structure contains the number of modes supported by a video adapter, and the size of the structure that describes each mode.



## -syntax

````
typedef struct _VIDEO_NUM_MODES {
  ULONG NumModes;
  ULONG ModeInformationLength;
} VIDEO_NUM_MODES, *PVIDEO_NUM_MODES;
````


## -struct-fields

### -field NumModes

Specifies the number of modes supported by the device.


### -field ModeInformationLength

Is the length, in bytes, of the <a href="display.video_mode_information">VIDEO_MODE_INFORMATION</a> structure that describes each of the modes supported by the device.


## -remarks
The miniport driver returns a VIDEO_NUM_MODES structure in response to an <a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_num_avail_modes.md">IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES</a> request.


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

## -see-also
<dl>
<dt>
<a href="display.video_mode_information">VIDEO_MODE_INFORMATION</a>
</dt>
<dt>
<a href="..\ntddvdeo\ni-ntddvdeo-ioctl_video_query_num_avail_modes.md">IOCTL_VIDEO_QUERY_NUM_AVAIL_MODES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VIDEO_NUM_MODES structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

