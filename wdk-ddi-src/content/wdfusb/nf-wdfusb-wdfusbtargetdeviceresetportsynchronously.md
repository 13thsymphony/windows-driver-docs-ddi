---
UID: NF:wdfusb.WdfUsbTargetDeviceResetPortSynchronously
title: WdfUsbTargetDeviceResetPortSynchronously function
author: windows-driver-content
description: The WdfUsbTargetDeviceResetPortSynchronously method resets the USB port that is associated with the specified USB device.
old-location: wdf\wdfusbtargetdeviceresetportsynchronously.htm
old-project: wdf
ms.assetid: 4f0941ea-ccbb-4345-82c0-ec5d88862b05
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfUsbTargetDeviceResetPortSynchronously
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfUsbTargetDeviceResetPortSynchronously
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceResetPortSynchronously function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceResetPortSynchronously</b> method resets the USB port that is associated with the specified USB device.



## -syntax

````
NTSTATUS WdfUsbTargetDeviceResetPortSynchronously(
  _In_ WDFUSBDEVICE UsbDevice
);
````


## -parameters

### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


## -returns
<b>WdfUsbTargetDeviceResetPortSynchronously</b> returns the USB I/O target's completion status value if the operation succeeds. Otherwise, this method can return one of the following values:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The caller's IRQL was invalid.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
The <b>WdfUsbTargetDeviceResetPortSynchronously</b> method resets the USB port by sending an <a href="https://msdn.microsoft.com/library/windows/hardware/ff537269">IOCTL_INTERNAL_USB_RESET_PORT</a> request.

Before the framework resets the I/O target's USB port, it cancels all I/O requests that remain in the I/O target's queue. The driver must not send additional I/O requests to the I/O target until <b>WdfUsbTargetDeviceResetPortSynchronously</b> returns.

The driver must call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstop.md">WdfIoTargetStop</a> before it calls <b>WdfUsbTargetDeviceResetPortSynchronously</b>. After <b>WdfUsbTargetDeviceResetPortSynchronously</b> returns, the driver can call <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetstart.md">WdfIoTargetStart</a>.

After a successful reset operation, the bus driver reselects the configuration and any alternate interface settings that the device had before the reset operation occurred.

For more information about the <b>WdfUsbTargetDeviceResetPortSynchronously</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.

The following code example resets a specified device's USB port.


## -see-also
<dl>
<dt>
<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceResetPortSynchronously method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

