---
UID : NF:video.VideoPortAssociateEventsWithDmaHandle
title : VideoPortAssociateEventsWithDmaHandle function
author : windows-driver-content
description : The VideoPortAssociateEventsWithDmaHandle function is obsolete in Windows 2000 and later.VideoPortAssociateEventsWithDmaHandle associates an event, which is shared by the video display driver and the video miniport driver, with a DMA handle.
old-location : display\videoportassociateeventswithdmahandle.htm
old-project : display
ms.assetid : d8a64a06-41b9-429b-a5ac-6de4996c702b
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : VideoPortAssociateEventsWithDmaHandle, VideoPortAssociateEventsWithDmaHandle function [Display Devices], VideoPort_Functions_0b61cb97-6bee-4882-83c9-1a56b8c2807b.xml, video/VideoPortAssociateEventsWithDmaHandle, display.videoportassociateeventswithdmahandle
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


# VideoPortAssociateEventsWithDmaHandle function
The <b>VideoPortAssociateEventsWithDmaHandle</b> function is <b>obsolete</b> in Windows 2000 and later.

<b>VideoPortAssociateEventsWithDmaHandle</b> associates an event, which is shared by the video display driver and the video miniport driver, with a DMA handle.

## Syntax

````
PDMA VideoPortAssociateEventsWithDmaHandle(
  _In_    PVOID                 HwDeviceExtension,
  _Inout_ PVIDEO_REQUEST_PACKET pVrp,
  _In_    PVOID                 MappedUserEvent,
  _In_    PVOID                 DisplayDriverEvent
);
````

## Parameters

`HwDeviceExtension`

Pointer to the miniport driver's device extension.

`pVrp`

Pointer to a <a href="..\video\ns-video-_video_request_packet.md">VIDEO_REQUEST_PACKET</a>.

`MappedUserEvent`

Is reserved for system use.

`DisplayDriverEvent`

Is reserved for system use.


## Return Value

<b>VideoPortAssociateEventsWithDmaHandle</b> always returns <b>NULL</b>.

## Remarks

See <a href="https://msdn.microsoft.com/fe6c2e16-d222-4948-b1df-34ed8d57d9d8">Bus-Master DMA in Video Miniport Drivers</a> for information about packet-based and common-buffer DMA transfers.

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