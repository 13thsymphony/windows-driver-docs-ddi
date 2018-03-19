---
UID: NC:usbcamdi.PCAM_PROCESS_RAW_FRAME_ROUTINE
title: PCAM_PROCESS_RAW_FRAME_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamProcessRawVideoFrame callback function decodes a raw video frame.
old-location: stream\camprocessrawvideoframe.htm
old-project: stream
ms.assetid: 98dd7262-e8f7-4e22-b19e-1a7fc56c8fe1
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamProcessRawVideoFrame, CamProcessRawVideoFrame callback function [Streaming Media Devices], PCAM_PROCESS_RAW_FRAME_ROUTINE, stream.camprocessrawvideoframe, usbcamdi/CamProcessRawVideoFrame, usbcmdpr_68fb4b0e-0f04-4af5-b0a6-38279f84f31a.xml
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	usbcamdi.h
api_name:
-	CamProcessRawVideoFrame
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PCAM_PROCESS_RAW_FRAME_ROUTINE callback function
<p class="CCE_Message">[CamProcessRawVideoFrame is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine_ex.md">CamProcessRawVideoFrameEx</a>.
]

A camera minidriver's <b>CamProcessRawVideoFrame</b> callback function decodes a raw video frame.

## Syntax

```
PCAM_PROCESS_RAW_FRAME_ROUTINE PcamProcessRawFrameRoutine;

NTSTATUS PcamProcessRawFrameRoutine(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext,
  PVOID FrameContext,
  PVOID FrameBuffer,
  ULONG FrameLength,
  PVOID RawFrameBuffer,
  ULONG RawFrameLength,
  ULONG NumberOfPackets,
  PULONG BytesReturned
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to the camera minidriver's device object created by the USB hub.

`DeviceContext`

Pointer to the camera minidriver's device context.

`FrameContext`

Pointer to the camera minidriver's frame context.

`FrameBuffer`

Pointer to the buffer that receives the final processed video frame. See the Remarks section for more information about how USBCAMD uses this parameter.

`FrameLength`

Specifies the length of the frame buffer (from the original read request) in bytes.

`RawFrameBuffer`

Pointer to the buffer containing the received USB packets. See the Remarks section for more information about how USBCAMD uses this parameter.

`RawFrameLength`

Specifies the length of <i>RawFrameBuffer</i> in bytes.

`NumberOfPackets`

Specifies the number of USB packets received into <i>RawFrameBuffer</i>.

`BytesReturned`

Pointer to the number of bytes transferred. The minidriver must set this to zero if it encounters any errors during processing, as described in <a href="https://msdn.microsoft.com/a66f4191-53ce-4ca2-aae7-8fb24a1a9a16">Data Flow Using Isochronous Pipes</a>. See the Remarks section for more information about how USBCAMD uses this parameter.


## Return Value

<b>CamProcessRawVideoFrame</b> returns STATUS_SUCCESS or an appropriate error code.

## Remarks

Before USBCAMD calls the minidriver's <b>CamProcessRawVideoFrame</b> callback, it sets the first DWORD in the buffer pointed to by the <i>FrameBuffer</i> parameter to the value <i>0xdeadbeef.</i> After calling the minidriver's <b>CamProcessRawVideoFrame</b> callback USBCAMD checks the first DWORD in the buffer pointed to by the <i>FrameBuffer</i> parameter for the value <i>0xdeadbeef</i> to determine if <b>CamProcessRawVideoFrame</b> successfully copied the video frame from the buffer pointed to by the <i>RawFrameBuffer</i> parameter into the buffer pointed to by the <i>FrameBuffer</i> parameter.

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

This function is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\usbcamdi\nc-usbcamdi-pcam_process_raw_frame_routine_ex.md">CamProcessRawVideoFrameEx</a>