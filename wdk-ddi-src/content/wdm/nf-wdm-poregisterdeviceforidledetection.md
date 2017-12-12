---
UID: NF.wdm.PoRegisterDeviceForIdleDetection
title: PoRegisterDeviceForIdleDetection function
author: windows-driver-content
description: The PoRegisterDeviceForIdleDetection routine enables or cancels idle detection and sets idle time-out values for a device.
old-location: kernel\poregisterdeviceforidledetection.htm
old-project: kernel
ms.assetid: f786fa36-1faa-4e12-aec1-872b44c01a85
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PoRegisterDeviceForIdleDetection
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PoRegisterDeviceForIdleDetection
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# PoRegisterDeviceForIdleDetection function



## -description
The <b>PoRegisterDeviceForIdleDetection</b> routine enables or cancels idle detection and sets idle time-out values for a device.



## -syntax

````
PULONG PoRegisterDeviceForIdleDetection(
  _In_ PDEVICE_OBJECT     DeviceObject,
  _In_ ULONG              ConservationIdleTime,
  _In_ ULONG              PerformanceIdleTime,
  _In_ DEVICE_POWER_STATE State
);
````


## -parameters

### -param DeviceObject [in]

A pointer to the driver-created <a href="kernel.device_object">DEVICE_OBJECT</a> for the device. On Windows 2000 and later systems, this parameter can point to a physical device object (<a href="wdkgloss.p#wdkgloss.pdo#wdkgloss.pdo"><i>PDO</i></a>) or a functional device object (<a href="wdkgloss.f#wdkgloss.fdo#wdkgloss.fdo"><i>FDO</i></a>). On Windows 98/Me, this parameter must point to the PDO of the underlying device.


### -param ConservationIdleTime [in]

Sets the time-out value (in seconds) to apply when the system power policy optimizes for energy conservation. Specify zero to disable idle detection when conservation policy is in effect.


### -param PerformanceIdleTime [in]

Sets the time-out value (in seconds) to apply when the system power policy optimizes for performance. Specify zero to disable idle detection when performance policy is in effect.


### -param State [in]

Specifies the <a href="https://msdn.microsoft.com/2229f34c-9b88-4e3e-802e-f7be2c7ef168">device power state</a> to be requested in an <a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a> request when either <i>ConservationIdleTime</i> or <i>PerformanceIdleTime</i> has been met. Possible values are the <a href="kernel.device_power_state">DEVICE_POWER_STATE</a> values.


## -returns
<b>PoRegisterDeviceForIdleDetection</b> returns a pointer to the idle counter to indicate that idle detection has been enabled. It returns <b>NULL</b> to indicate that idle detection has been disabled, that an idle counter could not be allocated, or that one or both of the time-out values were invalid.


## -remarks
<b>PoRegisterDeviceForIdleDetection</b> enables drivers to use the idle detection mechanism provided by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559829">power manager</a>. Drivers call <b>PoRegisterDeviceForIdleDetection</b> for any of the following reasons:

To enable idle detection for the device and set initial idle time-out values

To change the idle time-out values for a device

To disable idle detection for a device

After enabling a device for idle detection, a driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559755">PoSetDeviceBusy</a> whenever the device is in use, passing the non-<b>NULL</b> idle pointer returned by <b>PoRegisterDeviceForIdleDetection</b>. Calling <b>PoSetDeviceBusy</b> restarts the idle countdown. Note that a driver must not pass a <b>NULL</b> pointer to <b>PoSetDeviceBusy</b>.

Whenever the device satisfies the current idle time-out value, the power manager sends an <b>IRP_MN_SET_POWER</b> request to the top of the device stack, specifying device power state <i>State</i>. In response to the <a href="kernel.irp">IRP</a>, each driver performs any device-specific tasks required before the power state transition, then passes the IRP to the next-lower driver. When the IRP reaches the bus driver, that driver puts the device in the requested lower power state and completes the IRP.

<b>PoRegisterDeviceForIdleDetection</b> sets time-out values for both conservation and performance. The <i>ConservationIdleTime</i> value applies when the system power policy optimizes for conservation; the <i>PerformanceIdleTime</i> value applies when the system power policy optimizes for performance. Typically, the applicable policy depends upon the power source: when running with AC power, the system optimizes for performance, and when running off a battery, the system optimizes for conservation. 

Certain devices can specify time-out values of -1 to use the standard power policy time-outs for their device class. The standard time-out values provide for better system integration for supported standard device classes. At present, WDM supports this feature for devices of type FILE_DEVICE_DISK and FILE_DEVICE_MASS_STORAGE. <b>PoRegisterDeviceForIdleDetection</b> returns <b>NULL</b> if -1 is specified for a device of an unsupported type. (For information about device types, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563821">Specifying Device Types</a>.)

Only one idle detection can be set per device. Subsequent calls to <b>PoRegisterDeviceForIdleDetection</b> change the idle detection values.

If both <i>ConservationIdleTime</i> and <i>PerformanceIdleTime</i> are zero, this routine cancels all idle detection for the device and returns <b>NULL</b>.

<b>PoRegisterDeviceForIdleDetection</b> can free a driver from the need to perform its own idle detection. However, drivers can also implement their own idle detection.


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
Version

</th>
<td width="70%">
Available starting with Windows 2000.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.irp">IRP</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551744">IRP_MN_SET_POWER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559755">PoSetDeviceBusy</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoRegisterDeviceForIdleDetection routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

