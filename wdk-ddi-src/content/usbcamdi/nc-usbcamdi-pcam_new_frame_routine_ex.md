---
UID: NC:usbcamdi.PCAM_NEW_FRAME_ROUTINE_EX
title: PCAM_NEW_FRAME_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamNewVideoFrameEx callback function initializes a new video frame context structure.
old-location: stream\camnewvideoframeex.htm
old-project: stream
ms.assetid: 739e434e-9621-4927-bf1d-2e7c3b2828d7
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamNewVideoFrameEx, CamNewVideoFrameEx routine [Streaming Media Devices], PCAM_NEW_FRAME_ROUTINE_EX, stream.camnewvideoframeex, usbcamdi/CamNewVideoFrameEx, usbcmdpr_e7d56a12-73a6-4778-91be-24962683c475.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: usbcamdi.h
req.include-header: Usbcamdi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL (See Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbcamdi.h
api_name:
-	CamNewVideoFrameEx
product:
- Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PCAM_NEW_FRAME_ROUTINE_EX callback function
A camera minidriver's <b>CamNewVideoFrameEx</b> callback function initializes a new video frame context structure.

## Syntax

```
PCAM_NEW_FRAME_ROUTINE_EX PcamNewFrameRoutineEx;

void PcamNewFrameRoutineEx(
  PVOID DeviceContext,
  PVOID FrameContext,
  ULONG StreamNumber,
  PULONG FrameLength
)
{...}
```

## Parameters

`DeviceContext`

Specifies the minidriver device context.

`FrameContext`

Specifies the frame context to be initialized.

`StreamNumber`

Indicates the stream associated with this new frame.

`FrameLength`

Pointer to the raw frame buffer length. The length is expressed in bytes. The camera minidriver may decrease this value if it does not require a buffer transfer on the USB bus of the specified size. The camera minidriver should not increase this value.


## Return Value

<b>CamNewVideoFrameEx</b> does not return a value.

## Remarks

USBCAMD calls the camera minidriver's <b>CamNewVideoFrameEx</b> callback function at IRQL = DISPATCH_LEVEL.

The original USBCAMD does not call <b>CamNewVideoFrameEx</b>.

This function is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |
| **IRQL** | DISPATCH_LEVEL (See Remarks section) |