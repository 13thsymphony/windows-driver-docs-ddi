---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_USBDEVICE_ADD
title: EVT_UCX_CONTROLLER_USBDEVICE_ADD
author: windows-driver-content
description: The client driver's implementation that UCX calls when a new USB device is detected.
old-location: buses\evt_ucx_controller_usbdevice_add.htm
old-project: usbref
ms.assetid: 0f89b57a-3374-4f40-88b5-43d233ba0e47
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ucx_controller_usbdevice_add, EvtUcxControllerUsbDeviceAdd callback function [Buses], EvtUcxControllerUsbDeviceAdd, EVT_UCX_CONTROLLER_USBDEVICE_ADD, EVT_UCX_CONTROLLER_USBDEVICE_ADD, ucxcontroller/EvtUcxControllerUsbDeviceAdd, PEVT_UCX_CONTROLLER_USBDEVICE_ADD callback function pointer [Buses], PEVT_UCX_CONTROLLER_USBDEVICE_ADD
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Ucxcontroller.h
apiname:
-	PEVT_UCX_CONTROLLER_USBDEVICE_ADD
product: Windows
targetos: Windows
req.typenames: "*PUCM_PD_REQUEST_DATA_OBJECT, UCM_PD_REQUEST_DATA_OBJECT"
req.product: Windows 10 or later.
---


# EVT_UCX_CONTROLLER_USBDEVICE_ADD function
The client driver's implementation that UCX calls when a new USB device is detected.

## Syntax

```
EVT_UCX_CONTROLLER_USBDEVICE_ADD EvtUcxControllerUsbdeviceAdd;

NTSTATUS EvtUcxControllerUsbdeviceAdd(
  UCXCONTROLLER UcxController,
  PUCXUSBDEVICE_INFO UcxUsbDeviceInfo,
  PUCXUSBDEVICE_INIT UsbDeviceInit
)
{...}
```

## Parameters

`UcxController`

A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

`UcxUsbDeviceInfo`

Pointer to a <a href="..\ucxusbdevice\ns-ucxusbdevice-_ucxusbdevice_info.md">UCXUSBDEVICE_INFO</a> structure.

`UsbDeviceInit`

Pointer to an opaque structure containing initialization
    information.  Callbacks for the device object are associated with this structure.
    This structure is managed by UCX.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks

The UCX client driver registers its <i>EVT_UCX_CONTROLLER_USBDEVICE_ADD</i> implementation with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

This callback function creates a new USB device object and registers the
    USB device object callback functions by calling
    <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>.  The function may need to allocate the common buffer that will be
    used as the device context.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxcontroller.h (include Ucxclass.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_CONTROLLER_USBDEVICE_ADD callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>