---
UID: NF:wdfdevice.WdfDeviceAssignS0IdleSettings
title: WdfDeviceAssignS0IdleSettings function
author: windows-driver-content
description: The WdfDeviceAssignS0IdleSettings method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.
old-location: wdf\wdfdeviceassigns0idlesettings.htm
old-project: wdf
ms.assetid: 78bb5b51-b5b2-4177-8965-e54c04881dd3
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceAssignS0IdleSettings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfDeviceAssignS0IdleSettings
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, FDOPowerPolicyOwnerAPI, KmdfIrql, KmdfIrql2, NonFDONotPowerPolicyOwnerAPI
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceAssignS0IdleSettings function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfDeviceAssignS0IdleSettings</b> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.



## -syntax

````
NTSTATUS WdfDeviceAssignS0IdleSettings(
  _In_ WDFDEVICE                              Device,
  _In_ PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS Settings
);
````


## -parameters

### -param Device [in]

A handle to a framework device object.


### -param Settings [in]

A pointer to a caller-supplied <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure. 


## -returns
If the operation succeeds, <b>WdfDeviceAssignS0IdleSettings</b> returns STATUS_SUCCESS. Additional return values include:
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The calling driver is not the device's power policy owner.

<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid <i>Settings</i> value is detected.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure is incorrect. 
<dl>
<dt><b>STATUS_POWER_STATE_INVALID</b></dt>
</dl>This value is returned if one of the following occurs:

Starting in KMDF version 1.11 running on Windows 8, the framework checks if the system's firmware can handle a wake signal while the system is in its fully on (S0) power state. If the machine fails this check, <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigns0idlesettings.md">WdfDeviceAssignS0IdleSettings</a> returns <b>STATUS_POWER_STATE_INVALID</b>, and the device remains in its fully on (D0) power state as long as the system remains in S0.

In this case, the driver should not return an error status value from <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> or any other runtime callback.  At most, the driver might log an error indicating that the device will consume more power than it normally would.

 

The method might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
If the driver sets the <b>IdleTimeoutType</b> member of <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> to <b>SystemManagedIdleTimeout</b> or <b>SystemManagedIdleTimeoutWithHint</b>, it must call <b>WdfDeviceAssignS0IdleSettings</b> before returning from <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>. Typically, a driver first calls <b>WdfDeviceAssignS0IdleSettings</b> from <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>.

 Additional calls to <b>WdfDeviceAssignS0IdleSettings</b> can be made at any time. However, after the driver  sets the value of the <b>IdleTimeoutType</b> member in its first call to <b>WdfDeviceAssignS0IdleSettings</b>, it must not change this value in later calls to this method.

If the driver registers for asynchronous notifications in <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> (for example by calling <a href="..\wdm\nf-wdm-poregisterpowersettingcallback.md">PoRegisterPowerSettingCallback</a> or <a href="..\wdm\nf-wdm-ioregisterplugplaynotification.md">IoRegisterPlugPlayNotification</a>), the driver must not subsequently call <b>WdfDeviceAssignS0IdleSettings</b> from within the driver callback routine that it registered.

For more information, see <a href="https://msdn.microsoft.com/d0ce51db-eeb7-45ef-b823-248cd03ee2a9">Supporting Idle Power-Down</a>.

The following code example initializes a <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure, sets an idle time-out value of 10 seconds, and calls <b>WdfDeviceAssignS0IdleSettings</b>.


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassignsxwakesettings.md">WdfDeviceAssignSxWakeSettings</a>
</dt>
<dt>
<a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceAssignS0IdleSettings method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

