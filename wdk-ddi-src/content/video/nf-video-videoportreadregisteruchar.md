---
UID: NF:video.VideoPortReadRegisterUchar
title: VideoPortReadRegisterUchar function
author: windows-driver-content
description: The VideoPortReadRegisterUchar function reads a byte from a mapped register.
old-location: display\videoportreadregisteruchar.htm
old-project: display
ms.assetid: 53270599-7e8e-491a-8d7b-05f550f100d3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortReadRegisterUchar, VideoPortReadRegisterUchar function [Display Devices], VideoPort_Functions_c8fea131-5f84-4f77-ab18-2ca8de12e598.xml, display.videoportreadregisteruchar, video/VideoPortReadRegisterUchar
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
-	VideoPortReadRegisterUchar
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortReadRegisterUchar function
The <b>VideoPortReadRegisterUchar</b> function reads a byte from a mapped register.

## Syntax

````
UCHAR VideoPortReadRegisterUchar(
   PUCHAR Register
);
````

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <a href="..\video\nf-video-videoportgetdevicebase.md">VideoPortGetDeviceBase</a>.


## Return Value

<b>VideoPortReadRegisterUchar</b> returns the byte read from the adapter.

## Remarks

A miniport driver's <a href="..\video\nc-video-pvideo_hw_interrupt.md">HwVidInterrupt</a> or <a href="..\video\nc-video-pminiport_synchronize_routine.md">HwVidSynchronizeExecutionCallback</a> function can call <b>VideoPortReadRegisterUchar</b>.

Callers of <b>VideoPortReadRegisterUchar</b> can be running at any IRQL, provided that the memory pointed to by the <i>Register</i> parameter is resident, mapped device memory.

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