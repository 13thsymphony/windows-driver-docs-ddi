---
UID: NC:usbcamdi.PCAM_FREE_BW_ROUTINE
title: PCAM_FREE_BW_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamFreeBandwidth callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.
old-location: stream\camfreebandwidth.htm
old-project: stream
ms.assetid: 360fd299-bb8a-4fbb-899d-0e5fbe228d80
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamFreeBandwidth, CamFreeBandwidth callback function [Streaming Media Devices], PCAM_FREE_BW_ROUTINE, stream.camfreebandwidth, usbcamdi/CamFreeBandwidth, usbcmdpr_bf8779db-a06c-49b8-aa2f-e558a53bfa93.xml
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
-	CamFreeBandwidth
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PCAM_FREE_BW_ROUTINE callback function
<p class="CCE_Message">[CamFreeBandwidth is not supported and may be altered or unavailable in the future. Instead, use <a href="..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine_ex.md">CamFreeBandwidthEx</a>.
]

A camera minidriver's <b>CamFreeBandwidth</b> callback function selects an alternate setting within the USB video streaming interface that uses no bandwidth.

## Syntax

```
PCAM_FREE_BW_ROUTINE PcamFreeBwRoutine;

NTSTATUS PcamFreeBwRoutine(
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

<b>CamFreeBandwidth</b> returns STATUS_SUCCESS or an appropriate error code.

## Remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="..\usbcamdi\ns-usbcamdi-_usbcamd_device_data.md">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamFreeBandwidth</b> callback function after the isochronous video stream has stopped.

Typically, this function calls the <b>USBCAMD_SelectAlternateInterface</b> service to select the correct alternate interface and prepare for streaming video.

This function is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="..\usbcamdi\nf-usbcamdi-usbcamd_selectalternateinterface.md">USBCAMD_SelectAlternateInterface</a>



<a href="..\usbcamdi\nc-usbcamdi-pcam_free_bw_routine_ex.md">CamFreeBandwidthEx</a>