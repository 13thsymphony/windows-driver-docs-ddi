---
UID: NF.wdfusb.WdfUsbTargetDeviceCyclePortSynchronously
title: WdfUsbTargetDeviceCyclePortSynchronously function
author: windows-driver-content
description: The WdfUsbTargetDeviceCyclePortSynchronously method power-cycles the USB port to which a specified device is attached.
old-location: wdf\wdfusbtargetdevicecycleportsynchronously.htm
old-project: wdf
ms.assetid: 8dee089c-1f1a-4090-8c43-8362bb684139
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WdfUsbTargetDeviceCyclePortSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.alt-api: WdfUsbTargetDeviceCyclePortSynchronously
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceCyclePortSynchronously function



## -description
<p class="CCE_Message">[Applies to KMDF only]
The <b>WdfUsbTargetDeviceCyclePortSynchronously</b> method power-cycles the USB port to which a specified device is attached.


## -syntax

````
NTSTATUS WdfUsbTargetDeviceCyclePortSynchronously(
  _In_ WDFUSBDEVICE UsbDevice
);
````


## -parameters

### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.

## -returns
<b>WdfUsbTargetDeviceCyclePortSynchronously</b> returns the I/O target's completion status value if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The caller's IRQL was invalid.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.



## -remarks
Power-cycling a port causes the device to be surprise-removed and re-enumerated. A driver might request a power cycle after it has loaded firmware into a device.

Before the framework cycles the I/O target's USB port, it cancels all I/O requests that remain in the I/O target's queue. The driver must not send additional I/O requests to the I/O target until <b>WdfUsbTargetDeviceCyclePortSynchronously</b> returns.

The driver must call <a href="wdf.wdfiotargetstop">WdfIoTargetStop</a> before it calls <b>WdfUsbTargetDeviceCyclePortSynchronously</b>.

For more information about the <b>WdfUsbTargetDeviceCyclePortSynchronously</b> method and USB I/O targets, see <a href="wdf.usb_i_o_targets">USB I/O Targets</a>.

The following code example power-cycles a specified device's USB port.

## -requirements
<table>
<tr>
<th width="30%">
Target platform
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfusb.h (include Wdfusb.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (see <a href="wdf.framework_library_versioning">Framework Library Versioning</a>.)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
PASSIVE_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_usbkmdfirql">UsbKmdfIrql</a>, <a href="devtest.kmdf_usbkmdfirql2">UsbKmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceCyclePortSynchronously method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
