---
UID: NC:udecxwdfdevice.EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY
title: EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY
author: windows-driver-content
description: The UDE client driver's implementation to determine the capabilities that are supported by the emulated USB host controller.
old-location: buses\evt_udecx_wdf_device_query_usb_capability.htm
old-project: UsbRef
ms.assetid: 96F3128C-C334-4531-9C86-3FA918A902AC
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.evt_udecx_wdf_device_query_usb_capability, EvtUdecxWdfDeviceQueryUsbCapability callback function [Buses], EvtUdecxWdfDeviceQueryUsbCapability, EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY, EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY, udecxwdfdevice/EvtUdecxWdfDeviceQueryUsbCapability
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	UdecxWdfDevice.h
apiname:
-	EvtUdecxWdfDeviceQueryUsbCapability
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_CALLBACKS, *PUDECX_USB_ENDPOINT_CALLBACKS
req.product: Windows 10 or later.
---


# EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY function
The UDE client driver's implementation to determine the capabilities that are supported by the emulated USB host controller.

## Syntax

```
EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY EvtUdecxWdfDeviceQueryUsbCapability;

_IRQL_requires_same_ NTSTATUS EvtUdecxWdfDeviceQueryUsbCapability(
  WDFDEVICE UdecxWdfDevice,
  PGUID CapabilityType,
  ULONG OutputBufferLength,
  PVOID OutputBuffer,
  PULONG ResultLength
)
{...}
```

## Parameters

`UdecxWdfDevice`

A handle to a framework device object that represents the controller. The client driver initialized this object in the previous call to <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>.

`CapabilityType`

Pointer to a GUID specifying the requested capability. The possible  <i>PGUID</i>  values are  as follows:

<ul>
<li>GUID_USB_CAPABILITY_CHAINED_MDLS</li>
<li>GUID_USB_CAPABILITY_SELECTIVE_SUSPEND</li>
<li>GUID_USB_CAPABILITY_FUNCTION_SUSPEND

</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE</li>
</ul>
   For information about the capabilities, see the Remarks section of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406230">USBD_QueryUsbCapability</a>.

`OutputBufferLength`

The length, in bytes, of the request's output buffer, if an output buffer is available.

`OutputBuffer`

A pointer to a location that receives the buffer's address. Certain capabilities may need to provide additional information
        to the USB device emulation  class extension (UdeCx)  in this buffer.

`ResultLength`

A location that, on return, contains the size, in bytes, of the information that the callback function stored in <i>OutputBuffer.</i>


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. If a capability is not supported, the client driver can return NT_SUCCESS(status) equals FALSE, such as STATUS_UNSUCCESSFUL.

## Remarks

The class extension invokes this callback function implemented by the client driver when the class extension receives a request to determine the emulated controller's capabilities. The callback is invoked only after <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> has returned, typically in <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>. This callback cannot be invoked after <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_release_hardware.md">EvtDeviceReleaseHardware</a> has returned. 

The class extension reports these capability GUIDs, as not supported: 

<ul>
<li>GUID_USB_CAPABILITY_STATIC_STREAMS</li>
<li>GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL</li>
</ul>
The class extension reports the GUID_USB_CAPABILITY_SELECTIVE_SUSPEND capability GUID as supported without even invoking the callback function.

For other GUIDs, the class extension invokes the client driver's implementation, such as GUID_USB_CAPABILITY_CHAINED_MDLS. The client driver is expected to determine support for I/O requests that use a chained MDL. If this capability is supported then, the <b>TransferBufferMdl</b> member of the <a href="..\usb\ns-usb-_urb.md">URB</a> contains the request buffer. If chained MDL is not supported, the client driver does not receive <b>TransferBufferMdl</b> values that  point to chained MDLs.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.15 |
| **Header** | udecxwdfdevice.h (include Udecx.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>