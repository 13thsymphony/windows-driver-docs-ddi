---
UID: NC:usbcamdi.PCAM_CONFIGURE_ROUTINE_EX
title: PCAM_CONFIGURE_ROUTINE_EX
author: windows-driver-content
description: A camera minidriver's CamConfigureEx callback function configures the isochronous streaming interface.
old-location: stream\camconfigureex.htm
old-project: stream
ms.assetid: ec9fd207-4ed8-4bc9-b240-b5214e8c7f67
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: CamConfigureEx, CamConfigureEx routine [Streaming Media Devices], PCAM_CONFIGURE_ROUTINE_EX, stream.camconfigureex, usbcamdi/CamConfigureEx, usbcmdpr_79d31303-32b2-493e-87b6-d6e1a9ad292d.xml
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
-	CamConfigureEx
product: Windows
targetos: Windows
req.typenames: USB_BUS_INTERFACE_USBDI_V3, *PUSB_BUS_INTERFACE_USBDI_V3
req.product: Windows 10 or later.
---


# PCAM_CONFIGURE_ROUTINE_EX callback function
A camera minidriver's <b>CamConfigureEx</b> callback function configures the isochronous streaming interface.

## Syntax

```
PCAM_CONFIGURE_ROUTINE_EX PcamConfigureRoutineEx;

NTSTATUS PcamConfigureRoutineEx(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext,
  PUSBD_INTERFACE_INFORMATION Interface,
  PUSB_CONFIGURATION_DESCRIPTOR ConfigurationDescriptor,
  ULONG PipeConfigListSize,
  PUSBCAMD_Pipe_Config_Descriptor PipeConfig,
  PUSB_DEVICE_DESCRIPTOR DeviceDescriptor
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to the camera minidriver's device object created by the USB hub.

`DeviceContext`

Pointer to the camera minidriver's device context.

`Interface`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a> structure initialized with the proper values for a SELECT_INTERFACE URB request. This interface structure corresponds to a single isochronous interface on the device.

`ConfigurationDescriptor`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a> for this device.

`PipeConfigListSize`

Specifies the number of elements in the <i>PipeConfig</i> array.

`PipeConfig`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568623">USBCAMD_Pipe_Config_Descriptor</a> array describing the association between pipes and streams.

`DeviceDescriptor`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a> for this device.


## Return Value

<b>CamConfigureEx</b> returns STATUS_SUCCESS or an appropriate error code.

## Remarks

Camera minidrivers use <b>CamConfigureEx</b> to inform USBCAMD about the relationship between discovered pipes and streams.

USBCAMD calls the <b>CamConfigureEx</b> callback function to configure the isochronous streaming interface. After this function returns, USBCAMD can be notified of which interface and which alternate setting within the USB video streaming interface to use for the idle state.

USBCAMD requires that the camera must have a single USB configuration description, and all alternate settings within the USB video streaming interface must have the same number and type of pipes.

The original USBCAMD does not call <b>CamConfigureEx</b>.

This function is required.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568590">USBCAMD_DEVICE_DATA2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568623">USBCAMD_Pipe_Config_Descriptor</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539068">USBD_INTERFACE_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>