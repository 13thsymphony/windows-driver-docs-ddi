---
UID: NF:udecxwdfdevice.UdecxWdfDeviceResetComplete
title: UdecxWdfDeviceResetComplete function
author: windows-driver-content
description: Informs the USB device emulation class extension (UdeCx) that the reset operation on the specified controller has competed.
old-location: buses\udecxwdfdeviceresetcomplete.htm
old-project: usbref
ms.assetid: B5873B19-17EF-4DF8-A3E7-7E7F6440A2B7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: UdecxWdfDeviceResetComplete
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
req.umdf-ver: 
req.alt-api: UdecxWdfDeviceResetComplete
req.alt-loc: Udecxstub.lib,Udecxstub.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Udecxstub.lib
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.typenames: *PUDECX_WDF_DEVICE_RESET_ACTION, UDECX_WDF_DEVICE_RESET_ACTION
req.product: Windows 10 or later.
---

# UdecxWdfDeviceResetComplete function



## -description
Informs the  USB device emulation  class extension (UdeCx) that the reset operation on the specified controller has competed.



## -syntax

````
void UdecxWdfDeviceResetComplete(
  _In_ WDFDEVICE Device
);
````


## -parameters

### -param Device [in]

A handle to a framework device object that represents the controller that has been reset. The client driver initialized this object in the previous call to <a href="..\udecxwdfdevice\nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation.md">UdecxWdfDeviceAddUsbDeviceEmulation</a>.


## -returns
This function does not return a value.


## -remarks

When the class extension calls the  <a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_reset.md">EVT_UDECX_WDF_DEVICE_RESET</a> callback function, that call is asynchronous. The client driver must call  <b>UdecxWdfDeviceResetComplete</b> to notify the class extension when the reset operation is complete with appropriate status information.



## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version

</th>
<td width="70%">
1.15

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>UdecxWdfDevice.h (include Udecx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Udecxstub.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\udecxwdfdevice\nc-udecxwdfdevice-evt_udecx_wdf_device_reset.md">EVT_UDECX_WDF_DEVICE_RESET</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595932">Architecture: USB Device Emulation (UDE)</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt595939">Write a UDE client driver</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UdecxWdfDeviceResetComplete function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

