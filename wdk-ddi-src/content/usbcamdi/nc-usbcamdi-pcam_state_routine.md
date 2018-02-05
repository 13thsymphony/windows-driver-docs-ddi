---
UID : NC:usbcamdi.PCAM_STATE_ROUTINE
title : PCAM_STATE_ROUTINE
author : windows-driver-content
description : A camera minidriver's state callback function restores a previously saved device context state or saves the current device context state.
old-location : stream\camrestorestate.htm
old-project : stream
ms.assetid : 9a69cace-11cc-4671-9e7c-df510cbdd16d
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : stream.camrestorestate, CamRestoreState, CamSaveState, MyCamState callback function [Streaming Media Devices], MyCamState, PCAM_STATE_ROUTINE, PCAM_STATE_ROUTINE, usbcamdi/MyCamState, usbcmdpr_74c8ba54-9be6-4512-a498-b49635db1760.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : usbcamdi.h
req.include-header : Usbcamdi.h
req.target-type : Desktop
req.target-min-winverclnt : Available on Windows operating system versions prior to Windows XP.
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUSB_BUS_INTERFACE_USBDI_V3, USB_BUS_INTERFACE_USBDI_V3"
req.product : Windows 10 or later.
---


# PCAM_STATE_ROUTINE callback function
<p class="CCE_Message">[CamRestoreState is not supported and may be altered or unavailable in the future. ]

A camera minidriver's state callback function restores a previously saved device context state or saves the current device context state.

## Syntax

```
PCAM_STATE_ROUTINE PcamStateRoutine;

NTSTATUS PcamStateRoutine(
  PDEVICE_OBJECT BusDeviceObject,
  PVOID DeviceContext
)
{...}
```

## Parameters

`BusDeviceObject`

Pointer to the camera minidriver's device object created by the USB hub.

For <b>CamSaveState</b>, this value can be NULL.

`DeviceContext`

Pointer to the camera minidriver's device context.


## Return Value

This callback routine must return STATUS_SUCCESS.

## Remarks

<b>About CamRestoreState</b>

USBCAMD calls the minidriver's <b>CamRestoreState</b> callback function in the context of an SRB_CHANGE_POWER_STATE request when the power state is going from OFF to ON (D3 to D0).

USBCAMD ignores the return value from the minidriver's <b>CamRestoreState</b>.

<b>CamRestoreState</b> is called by both versions 1.0 and 2.0 of USBCAMD.

This function is optional.

<b>About CamSaveState</b>

USBCAMD version 1.0 calls the minidriver's <b>CamSaveState</b> in the context of an SRB_CHANGE_POWER_STATE request where the power state is going from ON to OFF (D0 to D3).

USBCAMD ignores the return value from the minidriver's <b>CamSaveState</b> callback function.

<b>CamSaveState</b> is called by both versions 1.0 and 2.0 of USBCAMD.

This function is optional.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available on Windows operating system versions prior to Windows XP. Available on Windows operating system versions prior to Windows XP. |
| **Target Platform** | Desktop |
| **Header** | usbcamdi.h (include Usbcamdi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff568157">SRB_CHANGE_POWER_STATE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20PCAM_STATE_ROUTINE callback function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>