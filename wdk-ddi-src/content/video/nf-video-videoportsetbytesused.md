---
UID: NF:video.VideoPortSetBytesUsed
title: VideoPortSetBytesUsed function
author: windows-driver-content
description: The VideoPortSetBytesUsed function is obsolete in Windows 2000 and later.
old-location: display\videoportsetbytesused.htm
old-project: display
ms.assetid: da348cf9-5694-4e66-990e-bd07f259d97c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortSetBytesUsed, VideoPortSetBytesUsed function [Display Devices], VideoPort_Functions_5a8a1a59-b9a8-4b5b-b6d8-7139ddb9b474.xml, display.videoportsetbytesused, video/VideoPortSetBytesUsed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: video.h
req.include-header: Video.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows 2000 and later versions of the Windows operating systems.
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
req.lib: Videoprt.lib
req.dll: Videoprt.sys
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortSetBytesUsed
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortSetBytesUsed function
The <b>VideoPortSetBytesUsed</b> function is <b>obsolete</b> in Windows 2000 and later.

## Syntax

````
VOID VideoPortSetBytesUsed(
  _In_    PVOID HwDeviceExtension,
  _Inout_ PDMA  pDma,
  _In_    ULONG BytesUsed
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`pDma`

Pointer to a DMA handle. To obtain the appropriate DMA handle, use the value in the <b>OutputBuffer</b> member of the <i>pVrp</i> parameter after <a href="..\video\nf-video-videoportlockpages.md">VideoPortLockPages</a> returns.

`BytesUsed`

Specifies the number of bytes written to the buffer.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |

## See Also

<a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>



<a href="..\video\nf-video-videoportgetbytesused.md">VideoPortGetBytesUsed</a>