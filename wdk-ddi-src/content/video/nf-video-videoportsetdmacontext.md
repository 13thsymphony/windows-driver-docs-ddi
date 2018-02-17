---
UID: NF:video.VideoPortSetDmaContext
title: VideoPortSetDmaContext function
author: windows-driver-content
description: The VideoPortSetDmaContext function is obsolete in Windows 2000 and later.
old-location: display\videoportsetdmacontext.htm
old-project: display
ms.assetid: 4f357612-c07d-42fe-a49f-59acec80a8bc
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: VideoPort_Functions_8e20017f-9d32-45c9-8f68-10cc61b6591d.xml, VideoPortSetDmaContext, VideoPortSetDmaContext function [Display Devices], video/VideoPortSetDmaContext, display.videoportsetdmacontext
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	Videoprt.sys
apiname:
-	VideoPortSetDmaContext
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortSetDmaContext function
The <b>VideoPortSetDmaContext</b> function is <b>obsolete</b> in Windows 2000 and later.

## Syntax

````
VOID VideoPortSetDmaContext(
  _In_  PVOID HwDeviceExtension,
  _Out_ PDMA  pDma,
  _In_  PVOID InstanceContext
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`pDma`

Pointer to a DMA handle.

`InstanceContext`

Pointer to the DMA context to set.


## Return Value

None

## Remarks

See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |