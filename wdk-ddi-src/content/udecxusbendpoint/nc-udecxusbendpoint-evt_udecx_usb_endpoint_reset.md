---
UID : NC:udecxusbendpoint.EVT_UDECX_USB_ENDPOINT_RESET
title : EVT_UDECX_USB_ENDPOINT_RESET
author : windows-driver-content
description : The USB device emulation class extension (UdeCx) invokes this callback function to reset an endpoint of the virtual USB device.
old-location : buses\evt_udecx_usb_endpoint_reset.htm
old-project : usbref
ms.assetid : 4220509B-A378-47F4-8E71-0290EDED89EB
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : buses.evt_udecx_usb_endpoint_reset, EvtUsbEndpointReset callback function [Buses], EvtUsbEndpointReset, EVT_UDECX_USB_ENDPOINT_RESET, EVT_UDECX_USB_ENDPOINT_RESET, udecxusbendpoint/EvtUsbEndpointReset
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : udecxusbendpoint.h
req.include-header : Udecx.h
req.target-type : Windows
req.target-min-winverclnt : Windows 10
req.target-min-winversvr : Windows Server 2016
req.kmdf-ver : 1.15
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
req.irql : "<=DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PUDECX_USB_ENDPOINT_INIT_AND_METADATA, UDECX_USB_ENDPOINT_INIT_AND_METADATA"
req.product : Windows 10 or later.
---


# EVT_UDECX_USB_ENDPOINT_RESET function
The USB device emulation class extension (UdeCx) invokes this callback function to reset an endpoint of the virtual USB device.

## Syntax

```
EVT_UDECX_USB_ENDPOINT_RESET EvtUdecxUsbEndpointReset;

_IRQL_requires_same_ VOID EvtUdecxUsbEndpointReset(
  UDECXUSBENDPOINT UdecxUsbEndpoint,
  WDFREQUEST Request
)
{...}
```

## Parameters

`UdecxUsbEndpoint`

A handle to a UDE endpoint object that represents the endpoint to reset. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>.

`Request`

A handle to a framework request object that represents the request to reset the endpoint.


## Return Value

This callback function does not return a value.

## Remarks

The client driver registered this callback function in a previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointinitsetcallbacks.md">UdecxUsbEndpointInitSetCallbacks</a> by supplying a function pointer to its implementation.

The reset request clears the error condition in the endpoint that causes failed I/O transfers. At that time, UdeCx can invoke the  <i>EVT_UDECX_USB_ENDPOINT_RESET</i> callback function. That call is asynchronous. The client driver completes the request and signals completion with status by calling <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcompletewithinformation.md">WdfRequestCompleteWithInformation</a> method .  (this is the only way the UDECX client uses the request parameter).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxusbendpoint.h (include Udecx.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh968307">How to recover from USB pipe errors</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UDECX_USB_ENDPOINT_RESET callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>