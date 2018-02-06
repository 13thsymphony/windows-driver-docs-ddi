---
UID: NF:usbcamdi.USBCAMD_DriverEntry
title: USBCAMD_DriverEntry function
author: windows-driver-content
description: The USBCAMD_DriverEntry function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together.
old-location: stream\usbcamd_driverentry.htm
old-project: stream
ms.assetid: ac77b121-2495-4739-8c8f-96d6c48e4dc6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: USBCAMD_DriverEntry, stream.usbcamd_driverentry, usbcmdpr_3aeb66f4-1729-400c-af6d-6e1290c9fe3b.xml, usbcamdi/USBCAMD_DriverEntry, USBCAMD_DriverEntry function [Streaming Media Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.lib: Usbcamd2.lib
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	usbcamd2.lib
-	usbcamd2.dll
apiname:
-	USBCAMD_DriverEntry
product: Windows
targetos: Windows
req.typenames: "*PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3"
req.product: Windows 10 or later.
---


# USBCAMD_DriverEntry function
The <b>USBCAMD_DriverEntry</b> function registers the minidriver with USBCAMD, effectively binding USBCAMD and the minidriver together.

## Syntax

````
ULONG USBCAMD_DriverEntry(
  _In_ PVOID                           Context1,
  _In_ PVOID                           Context2,
  _In_ ULONG                           DeviceContextSize,
  _In_ ULONG                           FrameContextSize,
  _In_ PADAPTER_RECEIVE_PACKET_ROUTINE ReceivePacket
);
````

## Parameters

`Context1`

Pointer to the first argument that is passed to the camera minidriver's DriverEntry function. This is effectively a pointer to the driver object that is created by the system and passed to DriverEntry.

`Context2`

Pointer to the second argument that is passed to the camera minidriver's DriverEntry function. This is effectively a pointer to the registry path that describes the minidriver's registry key.

`DeviceContextSize`

Specifies the size, in bytes, required for the minidriver's device-specific context.

`FrameCOntextSize`

TBD

`ReceivePacket`

Pointer to the minidriver-defined <a href="..\usbcamdi\nc-usbcamdi-padapter_receive_packet_routine.md">AdapterReceivePacket</a> function that handles adapter-based SRB requests.


## Return Value

<b>USBCAMD_DriverEntry </b>returns the status of the registration attempt. If a value other than STATUS_SUCCESS is returned, the minidriver is unloaded.

## Remarks

A camera minidriver must call <b>USBCAMD_DriverEntry</b> from the minidriver's <b>DriverEntry</b> routine. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558717">DriverEntry for Stream Class Minidrivers</a>


<i>FrameContextSize</i> is optional. A non-<b>NULL</b> value should be provided only with calls to <a href="..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine.md">CamNewVideoFrame</a> or <a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine.md">CamProcessRawVideoFrame</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |
| **Library** | Usbcamd2.lib |

## See Also

<a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine.md">CamProcessRawVideoFrame</a>

<a href="..\usbcamdi\nc-usbcamdi-padapter_receive_packet_routine.md">AdapterReceivePacket</a>

<a href="..\usbcamdi\nc-usbcamdi-pcam_new_frame_routine.md">CamNewVideoFrame</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20USBCAMD_DriverEntry function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>