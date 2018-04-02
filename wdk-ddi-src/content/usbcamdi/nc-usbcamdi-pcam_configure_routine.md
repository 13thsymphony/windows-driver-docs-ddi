---
UID: NC:usbcamdi.PCAM_CONFIGURE_ROUTINE
title: PCAM_CONFIGURE_ROUTINE
author: windows-driver-content
description: A camera minidriver's CamConfigure callback function configures the isochronous streaming interface.
old-location: stream\camconfigure.htm
old-project: stream
ms.assetid: b17fa32e-0a58-4be4-a096-e486471c1cdd
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamConfigure, CamConfigure callback function [Streaming Media Devices], PCAM_CONFIGURE_ROUTINE, stream.camconfigure, usbcamdi/CamConfigure, usbcmdpr_4953051b-2fb0-4dd4-ac52-67da188ce7e1.xml
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
-	CamConfigure
product:
- Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PCAM_CONFIGURE_ROUTINE callback function
<p class="CCE_Message">[CamConfigure is not supported and may be altered or unavailable in the future. Instead, use <a href="https://msdn.microsoft.com/library/windows/hardware/ff557605">CamConfigureEx</a>.
]

A camera minidriver's <b>CamConfigure</b> callback function configures the isochronous streaming interface.

## Syntax

```
PCAM_CONFIGURE_ROUTINE PcamConfigureRoutine;

NTSTATUS PcamConfigureRoutine(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext,
  PUSBD_INTERFACE_INFORMATION Interface,
  PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  PLONG DataPipeIndex,
  PLONG SyncPipeIndex
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to the camera minidriver's device object created by the USB hub.

`DeviceContext`

Pointer to the camera minidriver's device context.

`Interface`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.

`ConfigurationDescriptor`

Pointer to an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a> for this device.

`DataPipeIndex`

Pointer to a value that indicates the index of the data pipe. The camera minidriver should fill in this value before returning.

`SyncPipeIndex`

Pointer to a value that indicates the index of the sync pipe, if one is needed. The camera minidriver should fill in this value before returning.


## Return Value

<b>CamConfigure</b> returns STATUS_SUCCESS or an appropriate error code.

## Remarks

Camera minidrivers that must maintain backward compatibility with the original USBCAMD must use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568585">USBCAMD_DEVICE_DATA</a> structure and its associated callback functions (that is, callback functions that do not contain the "Ex" suffix).

USBCAMD calls the camera minidriver's <b>CamConfigure</b> callback function to configure the isochronous streaming interface. After this function returns, USBCAMD can be notified of which interface and which alternate setting within the USB video streaming interface to use for the idle state.

This function is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557605">CamConfigureEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>