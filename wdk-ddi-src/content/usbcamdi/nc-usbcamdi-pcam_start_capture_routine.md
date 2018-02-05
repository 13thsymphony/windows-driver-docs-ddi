---
UID : NC:usbcamdi.PCAM_START_CAPTURE_ROUTINE
title : PCAM_START_CAPTURE_ROUTINE
author : windows-driver-content
description : A camera minidriver's CamStartCapture callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location : stream\camstartcapture.htm
old-project : stream
ms.assetid : e929f8c1-fe36-4374-976f-b0bfb3e0b4a2
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.camstartcapture, CamStartCapture, CamStartCapture callback function [Streaming Media Devices], CamStartCapture, PCAM_START_CAPTURE_ROUTINE, PCAM_START_CAPTURE_ROUTINE, usbcamdi/CamStartCapture, usbcmdpr_c4887b29-94a3-498f-ad6a-4f6a58bb8345.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : usbcamdi.h
req.include-header : Usbcamdi.h
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3"
req.product : Windows 10 or later.
---


# PCAM_START_CAPTURE_ROUTINE callback function
<p class="CCE_Message">[CamStartCapture is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine_ex.md">CamStartCaptureEx</a>.
]

A camera minidriver's <b>CamStartCapture</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.

## Syntax

```
PCAM_START_CAPTURE_ROUTINE PcamStartCaptureRoutine;

NTSTATUS PcamStartCaptureRoutine(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to camera minidriver's device object created by the USB hub.

`DeviceContext`

Pointer to camera minidriver's device context.


## Return Value

<b>CamStartCapture</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.

## Remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamStartCapture</b> callback function immediately prior to the start of the isochronous video capture stream. <b>CamStartCapture</b> is called in the context of a <b>Run</b> command.

This function is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a>

<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a>

<a href="..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine_ex.md">CamStartCaptureEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_START_CAPTURE_ROUTINE callback function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>