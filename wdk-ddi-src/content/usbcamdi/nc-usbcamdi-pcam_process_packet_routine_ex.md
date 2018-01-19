---
UID : NC:usbcamdi.PCAM_PROCESS_PACKET_ROUTINE_EX
title : PCAM_PROCESS_PACKET_ROUTINE_EX
author : windows-driver-content
description : A camera minidriver's CamProcessUSBPacketEx callback function processes a USB packet.
old-location : stream\camprocessusbpacketex.htm
old-project : stream
ms.assetid : 9f69b2f0-6e55-440f-98ab-35d8faddf933
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : _USB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
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
req.alt-api : CamProcessUSBPacketEx
req.alt-loc : usbcamdi.h
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
req.typenames : USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product : Windows 10 or later.
---


# PCAM_PROCESS_PACKET_ROUTINE_EX callback function
A camera minidriver's <b>CamProcessUSBPacketEx</b> callback function processes a USB packet.

## Syntax

```
PCAM_PROCESS_PACKET_ROUTINE_EX PcamProcessPacketRoutineEx;

ULONG PcamProcessPacketRoutineEx(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext,
  PVOID CurrentFrameContext,
  PUSBD_ISO_PACKET_DESCRIPTOR SyncPacket,
  PVOID SyncBuffer,
  PUSBD_ISO_PACKET_DESCRIPTOR DataPacket,
  PVOID DataBuffer,
  PBOOLEAN FrameComplete,
  PULONG PacketFlag,
  PULONG ValidDataOffset
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to the camera minidriver's device object created by the USB hub.

`DeviceContext`

Pointer to the camera minidriver's device context.

`CurrentFrameContext`

Pointer to the camera minidriver's frame context.

`SyncPacket`

Pointer to a <a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a> structure from the sync pipe. This value is <b>NULL</b> if the interface has only one pipe.

`SyncBuffer`

Pointer to the data for the <i>SyncPacket</i>.

`DataPacket`

Specifies the isochronous packet descriptor from data pipe.

`DataBuffer`

Pointer to <i>DataPacket.</i>

`FrameComplete`

Pointer to a BOOLEAN value that the camera minidriver sets to indicate whether this is the first data packet for a new video frame.

`PacketFlag`

Pointer to a value that the minidriver sets to indicate the contents of the current frame. It should be set to one of the following values:

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
USBCAMD_PROCESSPACKETEX_DropFrame

</td>
<td>
The current frame is unsalvageable. The read IRP should be recycled.

</td>
</tr>
<tr>
<td>
USBCAMD_PROCESSPACKETEX_NextFrameIsStill

</td>
<td>
The frame is a still image.

</td>
</tr>
<tr>
<td>
USBCAMD_PROCESSPACKETEX_CurrentFrameIsStill

</td>
<td>
The current frame is for the still pin.

</td>
</tr>
</table>

`ValidDataOffset`

Pointer to a ULONG value that indicates an offset from the beginning of the packet. USBCAMD should start the copy from this offset. This eliminates the extra buffer copy in the case of an in-band signal. If the camera is not using in-band signaling, <i>ValidDataOffset</i> should be set to zero.


## Return Value

This function returns the number of bytes that should be copied.

## Remarks

The minidriver should complete its <b>CamProcessUSBPacketEx</b> function as quickly as possible. Image processing should be deferred to the <a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine_ex.md">CamProcessRawVideoFrameEx</a> function.

This callback function is used with isochronous pipes only (video or still streaming).

The original USBCAMD does not call <b>CamProcessUSBPacketEx</b>.

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

<dl>
<dt>
<a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine_ex.md">CamProcessRawVideoFrameEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_PROCESS_PACKET_ROUTINE_EX routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>