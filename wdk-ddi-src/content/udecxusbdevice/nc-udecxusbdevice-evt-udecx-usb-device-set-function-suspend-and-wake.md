---
UID: NC.udecxusbdevice.EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE
title: EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to change the function state of the specified interface of the virtual USB 3.0 device.
old-location: buses\evt_udecx_usb_device_set_function_suspend_and_wake.htm
old-project: usbref
ms.assetid: 54484E17-AA96-4152-B672-94C29E53F352
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: UdecxUrbSetBytesCompleted
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: udecxusbdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: EvtUsbDeviceSetFunctionSuspendAndWake
req.alt-loc: udecxusbdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE callback



## -description
<p>The USB device emulation class extension (UdeCx) invokes this callback function when it gets a request to change the function state of  the specified interface of the virtual USB 3.0 device.</p>


## -prototype

````
EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE EvtUsbDeviceSetFunctionSuspendAndWake;

NTSTATUS EvtUsbDeviceSetFunctionSuspendAndWake(
  _In_ WDFDEVICE                       UdecxWdfDevice,
  _In_ UDECXUSBDEVICE                  UdecxUsbDevice,
  _In_ ULONG                           Interface,
  _In_ UDECX_USB_DEVICE_FUNCTION_POWER FunctionPower
)
{ ... }
````


## -parameters
<dl>

### -param UdecxWdfDevice [in]

<dd>
<p>A handle to a framework device object that represents the controller to which the USB device is attached. The client driver initialized this object in a previous call to <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>.</p>
</dd>

### -param UdecxUsbDevice [in]

<dd>
<p>A handle to UDE device object. The client driver created this object in a previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.</p>
</dd>

### -param Interface [in]

<dd>
<p>This value is the <b>bInterfaceNumber</b> of the interface that is waking up. </p>
</dd>

### -param FunctionPower [in]

<dd>
<p>A <a href="..\udecxusbdevice\ne-udecxusbdevice--udecx-usb-device-function-power.md">UDECX_USB_DEVICE_FUNCTION_POWER</a>-type value that indicates whether the interface can suspend and send wake signal to the host controller.</p>
</dd>
</dl>

## -returns
<p>If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE.</p>

## -remarks
<p>The client driver registered the function in a previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.</p>

<p>In the callback implementation, the client driver for the USB device is expected to perform steps to enter working state. </p>

<p>This event callback function applies to USB 3.0+ devices. UdeCx invokes this function to notify the client driver of a request to change the power state of a particular function. It also informs the driver whether or not the  function can wake from the new state.</p>

<p>The power request may be completed asynchronously by returning STATUS_PENDING, and then later completing it by calling <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicesetfunctionsuspendandwakecomplete.md">UdecxUsbDeviceSetFunctionSuspendAndWakeComplete</a> with the actual completion code.
</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.15</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Udecxusbdevice.h (include Udecx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.usb_emulated_device__ude__architecture">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="buses.writing_a_ude_client_driver">Write a UDE client driver</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UDECX_USB_DEVICE_SET_FUNCTION_SUSPEND_AND_WAKE callback function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
