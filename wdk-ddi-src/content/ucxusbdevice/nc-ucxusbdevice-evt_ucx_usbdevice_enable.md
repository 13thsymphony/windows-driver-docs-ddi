---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_ENABLE
title: EVT_UCX_USBDEVICE_ENABLE
author: windows-driver-content
description: The client driver's implementation that UCX calls to program information about the device and its default control endpoint into the controller.
old-location: buses\evt_ucx_usbdevice_enable.htm
old-project: usbref
ms.assetid: ac46a6eb-c30d-4b1f-8e14-0ae44ae0d4f1
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.evt_ucx_usbdevice_enable, EvtUcxUsbDeviceEnable callback function [Buses], EvtUcxUsbDeviceEnable, EVT_UCX_USBDEVICE_ENABLE, EVT_UCX_USBDEVICE_ENABLE, ucxusbdevice/EvtUcxUsbDeviceEnable, PEVT_UCX_USBDEVICE_ENABLE callback function pointer [Buses], PEVT_UCX_USBDEVICE_ENABLE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ucxusbdevice.h
apiname:
-	PEVT_UCX_USBDEVICE_ENABLE
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_INFO, STREAM_INFO"
req.product: Windows 10 or later.
---


# EVT_UCX_USBDEVICE_ENABLE function
The client driver's implementation that UCX calls to program information about the device and its default control endpoint
    into the controller.

## Syntax

```
EVT_UCX_USBDEVICE_ENABLE EvtUcxUsbdeviceEnable;

void EvtUcxUsbdeviceEnable(
  UCXCONTROLLER UcxController,
  WDFREQUEST Request
)
{...}
```

## Parameters

`UcxController`

A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

`Request`

A structure of type <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_enable.md">USBDEVICE_ENABLE</a>.


## Return Value

This callback function does not return a value.

## Remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.

To
    transition the device to the desired state, the host controller driver communicates with the hardware to complete the request.

In this callback function, the client driver prepares the controller to accept and schedule transfers on the default control
    endpoint for the USB device.

When the driver has finished, it completes the WDFREQUEST.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
UsbDevice_EvtUcxUsbDeviceEnable(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)
    
{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceEnable");

    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &amp;wdfRequestParams);
    usbDeviceEnable = (PUSBDEVICE_ENABLE)wdfRequestParams.Parameters.Others.Arg1;
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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_USBDEVICE_ENABLE callback function%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>