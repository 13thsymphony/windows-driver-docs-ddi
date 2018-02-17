---
UID: NC:ucxcontroller.EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
title: EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC
author: windows-driver-content
description: UCX invokes this callback to retrieves the system query performance counter (QPC) value synchronized with the frame and microframe.
old-location: buses\evt_ucx_controller_get_frame_number_and_qpc_for_time_sync.htm
old-project: usbref
ms.assetid: A8D666BD-5C2A-416F-901E-5FF7CF38A084
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.evt_ucx_controller_get_frame_number_and_qpc_for_time_sync, EvtUcxControllerGetFrameNumberAndQpcForTimeSync callback function [Buses], EvtUcxControllerGetFrameNumberAndQpcForTimeSync, EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC, EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC, ucxcontroller/EvtUcxControllerGetFrameNumberAndQpcForTimeSync
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
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
-	EvtUcxControllerGetFrameNumberAndQpcForTimeSync
product: Windows
targetos: Windows
req.typenames: "*PUCM_PD_REQUEST_DATA_OBJECT, UCM_PD_REQUEST_DATA_OBJECT"
req.product: Windows 10 or later.
---


# EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC function
UCX invokes this callback to retrieves the system query performance counter (QPC) value  synchronized with the  frame and microframe.

## Syntax

```
EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC EvtUcxControllerGetFrameNumberAndQpcForTimeSync;

void EvtUcxControllerGetFrameNumberAndQpcForTimeSync(
  UCXCONTROLLER UcxController,
  WDFREQUEST WdfRequest,
  size_t OutputBufferLength,
  size_t InputBufferLength
)
{...}
```

## Parameters

`UcxController`

A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

`WdfRequest`

A framework request object that contains the request to get the synchronized frame and microframe number.

`OutputBufferLength`

The length, in bytes, of the request's output buffer, if an output buffer
        is available. This value is the size of the <a href="..\usbioctl\ns-usbioctl-_usb_frame_number_and_qpc_for_time_sync_information.md">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure.

`InputBufferLength`

The length, in bytes, of the request's input buffer, if an input buffer
        is available. This value is the size of the <a href="..\usbioctl\ns-usbioctl-_usb_frame_number_and_qpc_for_time_sync_information.md">USB_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC_INFORMATION</a> structure.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10, version 1709 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxcontroller.h (include Ucxclass.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_frame_number_and_qpc_for_time_sync.md">IOCTL_USB_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_CONTROLLER_GET_FRAME_NUMBER_AND_QPC_FOR_TIME_SYNC callback function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>