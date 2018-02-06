---
UID: NF:video.VideoPortSignalDmaComplete
title: VideoPortSignalDmaComplete function
author: windows-driver-content
description: The VideoPortSignalDmaComplete function is obsolete in Windows 2000 and later.VideoPortSignalDmaComplete indicates to the video miniport driver whether the current DMA transfer is complete.
old-location: display\videoportsignaldmacomplete.htm
old-project: display
ms.assetid: 81730acb-ff15-438d-8225-125283f61db2
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.videoportsignaldmacomplete, VideoPort_Functions_2246061c-11be-4eca-94bf-3b788dddd420.xml, VideoPortSignalDmaComplete, video/VideoPortSignalDmaComplete, VideoPortSignalDmaComplete function [Display Devices]
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
-	VideoPortSignalDmaComplete
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_SERVICES
req.product: Windows 10 or later.
---


# VideoPortSignalDmaComplete function
The <b>VideoPortSignalDmaComplete</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortSignalDmaComplete</b> indicates to the video miniport driver whether the current DMA transfer is complete.

## Syntax

````
BOOLEAN VideoPortSignalDmaComplete(
  _In_ PVOID HwDeviceExtension,
  _In_ PDMA  pDmaHandle
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`pDmaHandle`

Pointer to a DMA handle. To obtain the appropriate DMA handle, use the value in the <b>OutputBuffer</b> member of the <i>pVrp</i> parameter after <a href="..\video\nf-video-videoportlockpages.md">VideoPortLockPages</a> returns.


## Return Value

<b>VideoPortSignalDmaComplete</b> always returns <b>FALSE</b>.

## Remarks

See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows 2000 and later versions of the Windows operating systems. Available in Windows 2000 and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | video.h (include Video.h) |
| **Library** | Videoprt.lib |
| **DLL** | Videoprt.sys |