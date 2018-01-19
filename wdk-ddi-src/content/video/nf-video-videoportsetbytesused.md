---
UID : NF:video.VideoPortSetBytesUsed
title : VideoPortSetBytesUsed function
author : windows-driver-content
description : The VideoPortSetBytesUsed function is obsolete in Windows 2000 and later.
old-location : display\videoportsetbytesused.htm
old-project : display
ms.assetid : da348cf9-5694-4e66-990e-bd07f259d97c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VideoPortSetBytesUsed
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : video.h
req.include-header : Video.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows 2000 and later versions of the Windows operating systems.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : VideoPortSetBytesUsed
req.alt-loc : Videoprt.sys
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Videoprt.lib
req.dll : Videoprt.sys
req.irql : 
req.typenames : VIDEO_PORT_SERVICES
req.product : Windows 10 or later.
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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | video.h (include Video.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\video\nf-video-videoportgetbytesused.md">VideoPortGetBytesUsed</a>
</dt>
<dt>
<a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortSetBytesUsed function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>