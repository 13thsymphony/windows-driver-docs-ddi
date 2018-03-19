---
UID: NF:video.VideoPortReadPortBufferUshort
title: VideoPortReadPortBufferUshort function
author: windows-driver-content
description: The VideoPortReadPortBufferUshort function reads a number of USHORT values from a mapped I/O port and writes them into a buffer.
old-location: display\videoportreadportbufferushort.htm
old-project: display
ms.assetid: 3ad19dc0-f301-4367-b867-6bc714fd3d5e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortReadPortBufferUshort, VideoPortReadPortBufferUshort function [Display Devices], VideoPort_Functions_598e11ff-25be-4b55-a86f-130100ed0972.xml, display.videoportreadportbufferushort, video/VideoPortReadPortBufferUshort
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
req.irql: See Remarks section.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortReadPortBufferUshort
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortReadPortBufferUshort function
The <b>VideoPortReadPortBufferUshort</b> function reads a number of USHORT values from a mapped I/O port and writes them into a buffer.

## Syntax

````
VOID VideoPortReadPortBufferUshort(
        PUSHORT Port,
  _Out_ PUSHORT Buffer,
        ULONG   Count
);
````

## Parameters

`Port`

Pointer to the port. The given <i>Port</i> must be in a mapped I/O-space range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.

`Buffer`

Pointer to a buffer into which an array of USHORT values is written.

`Count`

Specifies the number of USHORT values to be written to the buffer.


## Return Value

None

## Remarks

The buffer must be large enough to contain at least the specified number of USHORT values.

A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadPortBufferUshort</b>.

Callers of <b>VideoPortReadPortBufferUshort</b> can be running at any IRQL, provided that the memory pointed to by the <i>Buffer</i> parameter is resident and that pointed to by the <i>Port</i> parameter is resident, mapped device memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | See Remarks section. |

## See Also

<a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>



<a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a>



<a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a>