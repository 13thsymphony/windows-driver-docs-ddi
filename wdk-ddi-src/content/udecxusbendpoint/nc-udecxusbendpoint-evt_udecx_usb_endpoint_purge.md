---
UID : NC:udecxusbendpoint.EVT_UDECX_USB_ENDPOINT_PURGE
title : EVT_UDECX_USB_ENDPOINT_PURGE
author : windows-driver-content
description : The USB device emulation class extension (UdeCx) invokes this callback function to stop queuing I/O requests to the endpoint's queue and cancel unprocessed requests.
old-location : buses\evt_udecx_usb_endpoint_purge.htm
old-project : usbref
ms.assetid : FAC021F0-CF37-4A28-BE89-D6BD77B8B708
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _UDECX_USB_ENDPOINT_INIT_AND_METADATA, *PUDECX_USB_ENDPOINT_INIT_AND_METADATA, UDECX_USB_ENDPOINT_INIT_AND_METADATA
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
req.alt-api : EvtUsbEndpointPurge
req.alt-loc : UdecxUsbEndpoint.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <=DISPATCH_LEVEL
req.typenames : "*PUDECX_USB_ENDPOINT_INIT_AND_METADATA, UDECX_USB_ENDPOINT_INIT_AND_METADATA"
req.product : Windows 10 or later.
---


# EVT_UDECX_USB_ENDPOINT_PURGE function
The USB device emulation class extension (UdeCx) invokes this callback function to stop queuing I/O requests to the endpoint's queue and cancel unprocessed requests.

## Syntax

```
EVT_UDECX_USB_ENDPOINT_PURGE EvtUdecxUsbEndpointPurge;

_IRQL_requires_same_ VOID EvtUdecxUsbEndpointPurge(
  UDECXUSBENDPOINT UdecxUsbEndpoint
)
{...}
```

## Parameters

`UdecxUsbEndpoint`

A handle to a UDE endpoint object that represents the endpoint for which I/O requests must be canceled. The client driver retrieved this pointer in the previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointcreate.md">UdecxUsbEndpointCreate</a>.


## Return Value

This callback function does not return a value.

## Remarks

The client driver registered this callback function in a previous call to <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointinitsetcallbacks.md">UdecxUsbEndpointInitSetCallbacks</a> by supplying a function pointer to its implementation.

In the implementation, the client driver is required to ensure all I/O forwarded from the endpoint’s queue has been completed, and that newly forwarded I/O request fail, until UdeCx invokes <a href="..\udecxusbendpoint\nc-udecxusbendpoint-evt_udecx_usb_endpoint_start.md">EVT_UDECX_USB_ENDPOINT_START</a>. Typically, those tasks are achieved by calling <a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>. This call is asynchronous and the client river must call <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointpurgecomplete.md">UdecxUsbEndpointPurgeComplete</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Minimum UMDF version** |  |
| **Header** | udecxusbendpoint.h (include Udecx.h) |
| **Library** |  |
| **IRQL** | <=DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="https://msdn.microsoft.com/83cc87c8-7e2d-4f79-a580-0519d327e7ba">Managing I/O Queues</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UDECX_USB_ENDPOINT_PURGE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>