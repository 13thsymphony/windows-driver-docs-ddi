---
UID: NC:usbcamdi.PCAM_START_CAPTURE_ROUTINE
title: PCAM_START_CAPTURE_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamStartCapture callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camstartcapture.htm
old-project: stream
ms.assetid: e929f8c1-fe36-4374-976f-b0bfb3e0b4a2
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: _USB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
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
req.alt-api: CamStartCapture
req.alt-loc: usbcamdi.h
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
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---

# PCAM_START_CAPTURE_ROUTINE callback



## -description
<p class="CCE_Message">[CamStartCapture is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine_ex.md">CamStartCaptureEx</a>.
]

A camera minidriver's <b>CamStartCapture</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.



## -prototype

````
NTSTATUS CamStartCapture(
   PDEVICE_OBJECT BusDeviceObject,
   PVOID          DeviceContext
);
````


## -parameters

### -param BusDeviceObject 

Pointer to camera minidriver's device object created by the USB hub.


### -param DeviceContext 

Pointer to camera minidriver's device context.


## -returns
<b>CamStartCapture</b> returns STATUS_SUCCESS or an appropriate error code. This return value is the completion code for the read IRP.


## -remarks
Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamStartCapture</b> callback function immediately prior to the start of the isochronous video capture stream. <b>CamStartCapture</b> is called in the context of a <b>Run</b> command.

This function is required.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Usbcamdi.h (include Usbcamdi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_start_capture_routine_ex.md">CamStartCaptureEx</a>
</dt>
<dt>
<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data2.md">USBCAMD_DEVICE_DATA2</a>
</dt>
<dt>
<a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_START_CAPTURE_ROUTINE callback function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

