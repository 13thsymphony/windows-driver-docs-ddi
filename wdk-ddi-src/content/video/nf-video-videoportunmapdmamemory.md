---
UID : NF:video.VideoPortUnmapDmaMemory
title : VideoPortUnmapDmaMemory function
author : windows-driver-content
description : The VideoPortUnmapDmaMemory function is obsolete in Windows 2000 and later.VideoPortUnmapDmaMemory unmaps a range of memory previously mapped by VideoPortMapDmaMemory.
old-location : display\videoportunmapdmamemory.htm
old-project : display
ms.assetid : f3d05263-5e6b-4875-afff-1166928778db
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VideoPortUnmapDmaMemory, VideoPortUnmapDmaMemory function [Display Devices], video/VideoPortUnmapDmaMemory, VideoPort_Functions_f2162fff-c7a8-4dde-aa17-94377f0cf716.xml, display.videoportunmapdmamemory
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
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : VIDEO_PORT_SERVICES
req.product : Windows 10 or later.
---


# VideoPortUnmapDmaMemory function
The <b>VideoPortUnmapDmaMemory</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortUnmapDmaMemory</b> unmaps a range of memory previously mapped by <a href="..\video\nf-video-videoportmapdmamemory.md">VideoPortMapDmaMemory</a>.

## Syntax

````
BOOLEAN VideoPortUnmapDmaMemory(
   PVOID  HwDeviceExtension,
   PVOID  VirtualAddress,
   HANDLE ProcessHandle,
   PDMA   BoardMemoryHandle
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`VirtualAddress`

Pointer to a virtual address within the mapped range to be released.

`ProcessHandle`

Is the handle to the current process.

`BoardMemoryHandle`

Is the handle to adapter's memory.


## Return Value

<b>VideoPortUnmapDmaMemory</b> always <b>FALSE</b>.

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