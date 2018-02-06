---
UID: NF:video.VideoPortWritePortBufferUshort
title: VideoPortWritePortBufferUshort function
author: windows-driver-content
description: The VideoPortWritePortBufferUshort function writes a number of USHORT values to a mapped I/O port.
old-location: display\videoportwriteportbufferushort.htm
old-project: display
ms.assetid: d9be3108-27fe-4899-bf23-0f51d9309888
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPortWritePortBufferUshort, display.videoportwriteportbufferushort, video/VideoPortWritePortBufferUshort, VideoPortWritePortBufferUshort function [Display Devices], VideoPort_Functions_cf88884e-2891-4e82-b7e0-afaa605a2d65.xml
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
req.irql: Any level (see Remarks section)
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortWritePortBufferUshort
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortWritePortBufferUshort function
The <b>VideoPortWritePortBufferUshort</b> function writes a number of USHORT values to a mapped I/O port.

## Syntax

````
VOID VideoPortWritePortBufferUshort(
       PUSHORT Port,
  _In_ PUSHORT Buffer,
       ULONG   Count
);
````

## Parameters

`Port`

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.

`Buffer`

Pointer to a buffer containing the USHORT values to be written.

`Count`

Specifies the number of USHORT values to be transferred to the adapter.


## Return Value

None

## Remarks

A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortWritePortBufferUshort</b>.

Callers of <b>VideoPortWritePortBufferUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems. Available in Windows 2000 and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | Any level (see Remarks section) |

## See Also

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20VideoPortWritePortBufferUshort function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>