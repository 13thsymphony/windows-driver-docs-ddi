---
UID: NS.ntddvdeo._VIDEO_MODE
title: VIDEO_MODE
author: windows-driver-content
description: The VIDEO_MODE structure contains the requested VGA mode that an adapter should set. This structure is used in conjunction with IOCTL_VIDEO_SET_CURRENT_MODE.
old-location: display\video_mode.htm
old-project: display
ms.assetid: 01fad141-d023-4a3a-80ae-cb07985db8d1
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: VIDEO_MODE, VIDEO_MODE, *PVIDEO_MODE
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
req.alt-api: VIDEO_MODE
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
req.iface: 
---

# VIDEO_MODE structure



## -description
<p>The VIDEO_MODE structure contains the requested VGA mode that an adapter should set. This structure is used in conjunction with <a href="..\ntddvdeo\ni-ntddvdeo-ioctl-video-set-current-mode.md">IOCTL_VIDEO_SET_CURRENT_MODE</a>. </p>


## -syntax

````
typedef struct _VIDEO_MODE {
  ULONG RequestedMode;
} VIDEO_MODE, *PVIDEO_MODE;
````


## -struct-fields
<dl>

### -field <b>RequestedMode</b>

<dd>
<p>Is the mode that the miniport driver should set if possible. In addition, the two high-order bits can be set to request special behavior from the miniport driver as follows:</p>
<p></p>
<dl>

### -field <a id="VIDEO_MODE_ZERO_MEMORY"></a><a id="video_mode_zero_memory"></a>VIDEO_MODE_ZERO_MEMORY

<dd>
<p>Indicates that the miniport driver should zero the video memory in conjunction with the mode set.</p>
</dd>

### -field <a id="VIDEO_MODE_MAP_MEM_LINEAR"></a><a id="video_mode_map_mem_linear"></a>VIDEO_MODE_MAP_MEM_LINEAR

<dd>
<p>Indicates that the miniport driver should map the video memory in a linear fashion if the adapter supports such an operation.</p>
</dd>
</dl>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddvdeo.h (include Ntddvdeo.h)</dt>
</dl>
</td>
</tr>
</table>