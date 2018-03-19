---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_DISABLE
title: EVT_UCX_USBDEVICE_DISABLE
author: windows-driver-content
description: The client driver's implementation that UCX calls to release controller resources associated with the device and its default endpoint.
old-location: buses\evt_ucx_usbdevice_disable.htm
old-project: usbref
ms.assetid: 85aa1d5e-e660-4fd7-a58d-8d32bbd966f2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: EVT_UCX_USBDEVICE_DISABLE, EvtUcxUsbDeviceDisable, EvtUcxUsbDeviceDisable callback function [Buses], PEVT_UCX_USBDEVICE_DISABLE, PEVT_UCX_USBDEVICE_DISABLE callback function pointer [Buses], buses.evt_ucx_usbdevice_disable, ucxusbdevice/EvtUcxUsbDeviceDisable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxusbdevice.h
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ucxusbdevice.h
api_name:
-	PEVT_UCX_USBDEVICE_DISABLE
product: Windows
targetos: Windows
req.typenames: STREAM_INFO, *PSTREAM_INFO
req.product: Windows 10 or later.
---


# EVT_UCX_USBDEVICE_DISABLE callback function
The client driver's implementation that UCX calls to release controller resources associated with the device and its default endpoint.

## Syntax

```
EVT_UCX_USBDEVICE_DISABLE EvtUcxUsbdeviceDisable;

void EvtUcxUsbdeviceDisable(
  UCXCONTROLLER UcxController,
  WDFREQUEST Request
)
{...}
```

## Parameters

`UcxController`

A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

`Request`

A structure of type <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_disable.md">USBDEVICE_DISABLE</a>.


## Return Value

This callback function does not return a value.

## Remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.

When the client driver has released controller resources, it completes the WDFREQUEST.  After completion, the only callback function that UCX  calls referencing this USB device is <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_enable.md">EVT_UCX_USBDEVICE_ENABLE</a>.

  While the device is disabled, UCX does not schedule transfers
    for it.


To
    transition the device to the desired state, the host controller driver communicates with the hardware to complete the request.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
UsbDevice_EvtUcxUsbDeviceDisable(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)


{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceDisable");

    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &amp;wdfRequestParams);
    usbDeviceDisable = (PUSBDEVICE_DISABLE)wdfRequestParams.Parameters.Others.Arg1;
    ...

    WdfRequestComplete(Request, STATUS_SUCCESS);
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>