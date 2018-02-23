---
UID: NC:usbcamdi.PCAM_ALLOCATE_BW_ROUTINE
title: PCAM_ALLOCATE_BW_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamAllocateBandwidth callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.
old-location: stream\camallocatebandwidth.htm
old-project: stream
ms.assetid: 0dd01bf7-04a8-4d20-982a-1ec81076583f
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: stream.camallocatebandwidth, CamAllocateBandwidth, CamAllocateBandwidth callback function [Streaming Media Devices], CamAllocateBandwidth, PCAM_ALLOCATE_BW_ROUTINE, PCAM_ALLOCATE_BW_ROUTINE, usbcamdi/CamAllocateBandwidth, usbcmdpr_4e7b22dc-0f6d-4a9b-82df-61c14cae981b.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	usbcamdi.h
apiname:
-	CamAllocateBandwidth
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PCAM_ALLOCATE_BW_ROUTINE callback function
<p class="CCE_Message">[CamAllocateBandwidth is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine_ex.md">CamAllocateBandwidthEx</a>.
]

A camera minidriver's <b>CamAllocateBandwidth</b> callback function selects the appropriate alternate setting within the USB video streaming interface and prepares the device to stream.

## Syntax

```
PCAM_ALLOCATE_BW_ROUTINE PcamAllocateBwRoutine;

NTSTATUS PcamAllocateBwRoutine(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext,
  PULONG RawFrameLength,
  PVOID Format
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to the camera minidriver's device object created by the USB hub.

`DeviceContext`

Pointer to the camera minidriver's device context.

`RawFrameLength`

Specifies the size, of the raw frame data from the packet stream, in bytes.

`Format`

Pointer to a <a href="..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader.md">KS_DATAFORMAT_VIDEOINFOHEADER</a> structure that is associated with this stream.


## Return Value

<b>CamAllocateBandwidth</b> returns STATUS_SUCCESS or an appropriate error code.

## Remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamAllocateBandwidth</b> callback function immediately before the isochronous video capture stream is started. It is called in connection with a <b>Run</b> command.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

This function is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="..\usbcamdi\nf-usbcamdi-usbcamd_selectalternateinterface.md">USBCAMD_SelectAlternateInterface</a>



<a href="..\usbcamdi\nc-usbcamdi-pcam_allocate_bw_routine_ex.md">CamAllocateBandwidthEx</a>



<a href="..\ksmedia\ns-ksmedia-tagks_dataformat_videoinfoheader.md">KS_DATAFORMAT_VIDEOINFOHEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_ALLOCATE_BW_ROUTINE callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>