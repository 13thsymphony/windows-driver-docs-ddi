---
UID: NS:msviddrv.tag_video_stream_init_parms
title: tag_video_stream_init_parms
author: windows-driver-content
description: .
old-location: stream\video_stream_init_parms.htm
old-project: stream
ms.assetid: 0FEC5054-8045-4CE5-AA59-AE3D23568308
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: tag_video_stream_init_parms, VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: msviddrv.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: VIDEO_STREAM_INIT_PARMS
req.alt-loc: Msviddrv.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.typenames: VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS
---

# tag_video_stream_init_parms structure



## -description




## -syntax

````
typedef struct tag_video_stream_init_parms {
  DWORD  dwMicroSecPerFrame;
  DWORD  dwCallback;
  DWORD  dwCallbackInst;
  DWORD  dwFlags;
  HANDLE hVideo;
} VIDEO_STREAM_INIT_PARMS, *LPVIDEO_STREAM_INIT_PARMS;
````


## -struct-fields

### -field dwMicroSecPerFrame


### -field dwCallback


### -field dwCallbackInst


### -field dwFlags


### -field hVideo


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Msviddrv.h</dt>
</dl>
</td>
</tr>
</table>