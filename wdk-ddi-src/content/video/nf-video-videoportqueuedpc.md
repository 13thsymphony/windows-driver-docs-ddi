---
UID: NF:video.VideoPortQueueDpc
title: VideoPortQueueDpc function
author: windows-driver-content
description: The VideoPortQueueDpc function allows a miniport driver to queue a DPC.
old-location: display\videoportqueuedpc.htm
old-project: display
ms.assetid: 9715ff37-397b-4102-a363-443b8076f881
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: VideoPortQueueDpc, VideoPortQueueDpc function [Display Devices], VideoPort_Functions_133e8c8b-e445-4f83-ad93-7eb560047f3f.xml, display.videoportqueuedpc, video/VideoPortQueueDpc
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
req.irql: ">= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Videoprt.sys
api_name:
-	VideoPortQueueDpc
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortQueueDpc function
The <b>VideoPortQueueDpc</b> function allows a miniport driver to queue a DPC.

## Syntax

````
BOOLEAN VideoPortQueueDpc(
  _In_ PVOID                 HwDeviceExtension,
  _In_ PMINIPORT_DPC_ROUTINE CallbackRoutine,
  _In_ PVOID                 Context
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`CallbackRoutine`

Pointer to the miniport driver's <a href="..\video\nc-video-pminiport_dpc_routine.md">HwVidDpcRoutine</a> to be called when the DPC is scheduled. The callback routine must be nonpaged.

`Context`

Pointer to the miniport driver-supplied context that will be passed to <i>CallbackRoutine</i>.


## Return Value

<b>VideoPortQueueDpc</b> returns <b>TRUE</b> if the DPC is successfully queued, and <b>FALSE</b> otherwise.

## Remarks

The deferred procedure is run when the IRQL on the current processor drops below DISPATCH_LEVEL. Callers of <b>VideoPortQueueDpc</b> must be running at IRQL &gt;= DISPATCH_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |
| **IRQL** | ">= DISPATCH_LEVEL" |

## See Also

<a href="..\video\nc-video-pminiport_dpc_routine.md">HwVidDpcRoutine</a>