---
UID: NC.udecxusbdevice.EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE
title: EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE
author: windows-driver-content
description: The USB device emulation class extension (UdeCx) invokes this callback function to change the configuration by selecting an alternate setting, disabling current endpoints, or adding dynamic endpoints.
old-location: buses\evt_udecx_usb_device_endpoints_configure.htm
old-project: usbref
ms.assetid: 5E425011-BFC7-434C-9D0A-DB4481EC315F
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
req.alt-api: EvtUsbDeviceEndpointsConfigure
req.alt-loc: UdecxUsbDevice.h
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

# EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE callback



## -description
<p>The USB device emulation class extension (UdeCx) invokes this callback function to change the configuration by selecting an alternate setting, disabling current endpoints, or adding dynamic endpoints.</p>


## -prototype

````
EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE EvtUsbDeviceEndpointsConfigure;

void EvtUsbDeviceEndpointsConfigure(
  _In_ UDECXUSBDEVICE                    UdecxUsbDevice,
  _In_ WDFREQUEST                        Request,
  _In_ PUDECX_ENDPOINTS_CONFIGURE_PARAMS Params
)
{ ... }
````


## -parameters
<dl>

### -param UdecxUsbDevice [in]

<dd>
<p>A handle to UDE device object. The client driver created this object in a previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdevicecreate.md">UdecxUsbDeviceCreate</a>.</p>
</dd>

### -param Request [in]

<dd>
<p>A handle to a framework request object that represents the request.</p>
</dd>

### -param Params [in]

<dd>
<p>A pointer to a <a href="..\udecxusbdevice\ns-udecxusbdevice--udecx-endpoints-configure-params.md">UDECX_ENDPOINTS_CONFIGURE_PARAMS</a> structure that describes the configuration options.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>The client driver registered this callback function in a previous call to <a href="..\udecxusbdevice\nf-udecxusbdevice-udecxusbdeviceinitsetstatechangecallbacks.md">UdecxUsbDeviceInitSetStateChangeCallbacks</a> by supplying a function pointer to its implementation.</p>

<p>The class extension invokes this  callback function to request the client driver to configure one or more new endpoints into hardware, and/or informs the driver when one or more existing endpoints is no longer being used. </p>

<p>After creating endpoints, for each new endpoint, the client driver must call <a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointsetwdfioqueue.md">UdecxUsbEndpointSetWdfIoQueue</a> before completing the request.
</p>

<p>After releasing endpoints, the client driver should not use framework queue objects associated with the endpoints. The class extension considers those queues as purged to prevent future requests.
</p>

<p>The class extension  can also request a new configuration value or an alternate setting through this callback.</p>

<p>This call is asynchronous. The client driver must signals completion with status by completing the request passed by the class extension. 
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
<dt>UdecxUsbDevice.h (include Udecx.h)</dt>
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
<a href="..\udecxusbendpoint\nf-udecxusbendpoint-udecxusbendpointsetwdfioqueue.md">UdecxUsbEndpointSetWdfIoQueue</a>
</dt>
<dt>
<a href="buses.usb_emulated_device__ude__architecture">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="buses.writing_a_ude_client_driver">Write a UDE client driver</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UDECX_USB_DEVICE_ENDPOINTS_CONFIGURE callback function%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
