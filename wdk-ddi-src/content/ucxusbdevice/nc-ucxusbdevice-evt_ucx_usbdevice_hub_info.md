---
UID: NC:ucxusbdevice.EVT_UCX_USBDEVICE_HUB_INFO
title: EVT_UCX_USBDEVICE_HUB_INFO
author: windows-driver-content
description: The client driver's implementation that UCX calls to retrieve hub properties.
old-location: buses\evt_ucx_usbdevice_hub_info.htm
old-project: UsbRef
ms.assetid: 5bf8000d-63d8-4901-b3fc-d3c43cefe37e
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.evt_ucx_usbdevice_hub_info, EvtUcxUsbDeviceHubInfo callback function [Buses], EvtUcxUsbDeviceHubInfo, EVT_UCX_USBDEVICE_HUB_INFO, EVT_UCX_USBDEVICE_HUB_INFO, ucxusbdevice/EvtUcxUsbDeviceHubInfo, PEVT_UCX_USBDEVICE_HUB_INFO callback function pointer [Buses], PEVT_UCX_USBDEVICE_HUB_INFO
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
-	PEVT_UCX_USBDEVICE_HUB_INFO
product: Windows
targetos: Windows
req.typenames: "*PSTREAM_INFO, STREAM_INFO"
req.product: Windows 10 or later.
---


# EVT_UCX_USBDEVICE_HUB_INFO function
The client driver's implementation that UCX calls to
retrieve hub properties.

## Syntax

```
EVT_UCX_USBDEVICE_HUB_INFO EvtUcxUsbdeviceHubInfo;

void EvtUcxUsbdeviceHubInfo(
  UCXCONTROLLER UcxController,
  WDFREQUEST Request
)
{...}
```

## Parameters

`UcxController`

A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

`Request`

Contains the <a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_hub_info.md">USBDEVICE_HUB_INFO</a> structure.


## Return Value

This callback function does not return a value.

## Remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a> method.

If the USB device is not a hub, do not provide this callback.

The client driver returns completion status in <i>Request</i>.  The driver can complete the WDFREQUEST asynchronously.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
UsbDevice_EvtUcxUsbDeviceHubInfo(
    UCXCONTROLLER      UcxController,
    WDFREQUEST         Request
)

{
    UNREFERENCED_PARAMETER(UcxController);

    DbgTrace(TL_INFO, UsbDevice, "UsbDevice_EvtUcxUsbDeviceHubInfo");

    //
    // Retrieve the USBDEVICE_HUB_INFO pointer from the
    // IOCTL_INTERNAL_USB_USBDEVICE_HUB_INFO WdfRequest.
    //
    WDF_REQUEST_PARAMETERS_INIT(&amp;wdfRequestParams);
    WdfRequestGetParameters(WdfRequest, &amp;wdfRequestParams);

    hubInfo = (PUSBDEVICE_HUB_INFO)wdfRequestParams.Parameters.Others.Arg1;

    ....


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

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_hub_info.md">USBDEVICE_HUB_INFO</a>



<a href="..\ucxusbdevice\nf-ucxusbdevice-ucx_usbdevice_event_callbacks_init.md">UCX_USBDEVICE_EVENT_CALLBACKS_INIT</a>



<a href="..\ucxusbdevice\nf-ucxusbdevice-ucxusbdevicecreate.md">UcxUsbDeviceCreate</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_ucx_usbdevice_event_callbacks.md">UCX_USBDEVICE_EVENT_CALLBACKS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20EVT_UCX_USBDEVICE_HUB_INFO callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>