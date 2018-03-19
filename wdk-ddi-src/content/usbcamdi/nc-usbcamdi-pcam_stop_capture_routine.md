---
UID: NC:usbcamdi.PCAM_STOP_CAPTURE_ROUTINE
title: PCAM_STOP_CAPTURE_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamStopCapture callback function performs any processing after the stream is stopped.
old-location: stream\camstopcapture.htm
old-project: stream
ms.assetid: c4403edb-3035-469b-bdb9-c33882a1c90c
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamStopCapture, CamStopCapture callback function [Streaming Media Devices], PCAM_STOP_CAPTURE_ROUTINE, stream.camstopcapture, usbcamdi/CamStopCapture, usbcmdpr_56cc6085-dfff-4576-b19a-45683a7b62d8.xml
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbcamdi.h
api_name:
-	CamStopCapture
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PCAM_STOP_CAPTURE_ROUTINE callback function
<p class="CCE_Message">[CamStopCapture is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine_ex.md">CamStopCaptureEx</a>.
]

A camera minidriver's <b>CamStopCapture</b> callback function performs any processing after the stream is stopped.

## Syntax

```
PCAM_STOP_CAPTURE_ROUTINE PcamStopCaptureRoutine;

NTSTATUS PcamStopCaptureRoutine(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to the camera minidriver's device object created by the USB hub.

`DeviceContext`

Pointer to the camera minidriver's device context.


## Return Value

<b>CamStopCapture</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.

## Remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the minidriver's <b>CamStopCapture</b> callback function immediately after the isochronous video stream is stopped. Typically, a camera minidriver selects an alternate setting within the USB video streaming interface that uses no additional bandwidth.

This function is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="..\usbcamdi\nc-usbcamdi-pcam_stop_capture_routine_ex.md">CamStopCaptureEx</a>



<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a>