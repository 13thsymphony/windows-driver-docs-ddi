---
UID : NC:ucxroothub.EVT_UCX_ROOTHUB_CONTROL_URB
title : EVT_UCX_ROOTHUB_CONTROL_URB
author : windows-driver-content
description : The client driver uses this callback type to implement handlers that UCX calls when it receives feature control requests on the USB hub.
old-location : buses\evt_ucx_roothub_control_urb.htm
old-project : usbref
ms.assetid : 4463a68f-ef03-43a1-b3e2-7baf43f47e80
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, *PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ucxroothub.h
req.include-header : Ucxclass.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.alt-api : PEVT_UCX_ROOTHUB_CONTROL_URB
req.alt-loc : ucxroothub.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : DISPATCH_LEVEL
req.typenames : UCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS, *PUCX_ENDPOINT_ISOCH_TRANSFER_PATH_DELAYS
req.product : Windows 10 or later.
---


# EVT_UCX_ROOTHUB_CONTROL_URB function
The client driver uses this callback type to implement handlers that UCX calls when it receives feature control requests on the USB hub.

## Syntax

```
EVT_UCX_ROOTHUB_CONTROL_URB EvtUcxRoothubControlUrb;

void EvtUcxRoothubControlUrb(
  UCXROOTHUB UcxRootHub,
  WDFREQUEST Request
)
{...}
```

## Parameters

`UcxRootHub`

A handle to a UCX object that represents the root hub.

`Request`

Contains the <a href="..\usb\ns-usb-_urb.md">URB</a> for the feature request.


## Return Value

This callback function does not return a value.

## Remarks

The client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>
 method.

The driver either provides callbacks for all of the individual feature request types, as shown in the first example, or it can provide a single handler of type <i>EVT_UCX_ROOTHUB_CONTROL_URB</i> that UCX calls for all hub and port control transfers.

The client driver returns completion status in <i>Request</i> and in the USBD_STATUS
    in the URB header.  The driver can complete the WDFREQUEST asynchronously.

This example shows how to register callbacks for individual feature request types.

Here is a sample implementation of one of the URB-specific request handlers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxroothub.h (include Ucxclass.h) |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_ROOTHUB_CONTROL_URB callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>