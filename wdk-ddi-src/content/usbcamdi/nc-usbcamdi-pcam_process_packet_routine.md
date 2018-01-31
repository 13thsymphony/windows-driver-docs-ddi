---
UID : NC:usbcamdi.PCAM_PROCESS_PACKET_ROUTINE
title : PCAM_PROCESS_PACKET_ROUTINE
author : windows-driver-content
description : A camera minidriver's CamProcessUSBPacket callback function processes a USB packet.
old-location : stream\camprocessusbpacket.htm
old-project : stream
ms.assetid : 2b83d1b1-82f6-455b-b22a-ae9433dd9f27
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.camprocessusbpacket, CamProcessUSBPacket, CamProcessUSBPacket callback function [Streaming Media Devices], CamProcessUSBPacket, PCAM_PROCESS_PACKET_ROUTINE, PCAM_PROCESS_PACKET_ROUTINE, usbcamdi/CamProcessUSBPacket, usbcmdpr_7eeca66e-b106-4cb0-b0c3-d7d07d82d841.xml
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
req.irql : DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3"
req.product : Windows 10 or later.
---


# PCAM_PROCESS_PACKET_ROUTINE callback function
<p class="CCE_Message">[CamProcessUSBPacket is not supported and may be altered or unavailable in the future. Instead, use CamProcessUSBPacketEx.
]

A camera minidriver's <b>CamProcessUSBPacket</b> callback function processes a USB packet.

## Syntax

```
PCAM_PROCESS_PACKET_ROUTINE PcamProcessPacketRoutine;

ULONG PcamProcessPacketRoutine(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext,
  PVOID CurrentFrameContext,
  PUSBD_ISO_PACKET_DESCRIPTOR SyncPacket,
  PVOID SyncBuffer,
  PUSBD_ISO_PACKET_DESCRIPTOR DataPacket,
  PVOID DataBuffer,
  PBOOLEAN FrameComplete,
  PBOOLEAN NextFrameIsStill
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to the camera minidriver's device object created by the USB hub.

`DeviceContext`

Pointer to the camera minidriver's device context.

`CurrentFrameContext`

Pointer to the minidriver's frame context.

`SyncPacket`

Pointer to a <a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a> structure from the sync pipe. This value is <b>NULL</b> if the interface has only one pipe.

`SyncBuffer`

Pointer to the data for the <i>SyncPacket.</i>

`DataPacket`

Pointer to a <a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a> structure from the data pipe.

`DataBuffer`

Pointer to <i>DataPacket.</i>

`FrameComplete`

Pointer to a BOOLEAN value that the camera minidriver sets to indicate whether this is the first data packet for a new video frame. Set to <b>TRUE</b> if this is the first data packet for a new video frame.

`NextFrameIsStill`

Pointer to a BOOLEAN value that the camera minidriver sets to indicate whether the next frame is a still frame or not. This value should be set to <b>FALSE</b> if the video stream is providing a live image or <b>TRUE</b> if the next frame is a still image or an image capture stream.


## Return Value

This callback function returns a ULONG that indicates the number of bytes that should be copied into the buffer (<i>RawFrameBuffer</i> or <i>FrameBuffer)</i>.

## Remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

The minidriver should complete this function as quickly as possible. Image processing should be deferred to the <a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine.md">CamProcessRawVideoFrame</a> function.

This function is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | usbcamdi.h (include Usbcamdi.h) |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\usbcamdi\nc-usbcamdi-pcam_process_packet_routine_ex.md">CamProcessUSBPacketEx</a>

<a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine.md">CamProcessRawVideoFrame</a>

<a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_PROCESS_PACKET_ROUTINE callback function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>