---
UID: NC:usbcamdi.PCAM_NEW_FRAME_ROUTINE
title: PCAM_NEW_FRAME_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamNewVideoFrame callback function initializes a new video frame context structure.
old-location: stream\camnewvideoframe.htm
old-project: stream
ms.assetid: b647cc94-e5eb-494f-b103-22aa30da8946
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamNewVideoFrame, CamNewVideoFrame callback function [Streaming Media Devices], PCAM_NEW_FRAME_ROUTINE, stream.camnewvideoframe, usbcamdi/CamNewVideoFrame, usbcmdpr_5f488227-2c1a-497e-975a-dc2b388f8489.xml
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
-	CamNewVideoFrame
product:
- Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PCAM_NEW_FRAME_ROUTINE callback function
<p class="CCE_Message">[CamNewVideoFrame is not supported and may be altered or unavailable in the future. Instead, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff557620">CamNewVideoFrameEx</a>.
]

A camera minidriver's <b>CamNewVideoFrame</b> callback function initializes a new video frame context structure.

## Syntax

```
PCAM_NEW_FRAME_ROUTINE PcamNewFrameRoutine;

void PcamNewFrameRoutine(
  PVOID DeviceContext,
  PVOID FrameContext
)
{...}
```

## Parameters

`DeviceContext`

Pointer to the camera minidriver's device context.

`FrameContext`

Pointer to the camera minidriver's frame context.


## Return Value

<b>CamNewVideoFrame</b> does not return a value.

## Remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568585">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamNewVideoFrame</b> callback function at IRQL = DISPATCH_LEVEL.

This function is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |
| **IRQL** | DISPATCH_LEVEL (See Remarks section) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557620">CamNewVideoFrameEx</a>