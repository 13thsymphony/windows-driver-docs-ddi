---
UID: NF:wdfdevice.WdfDeviceWdmAssignPowerFrameworkSettings
title: WdfDeviceWdmAssignPowerFrameworkSettings function
author: windows-driver-content
description: The WdfDeviceWdmAssignPowerFrameworkSettings method registers power management framework (PoFx) settings for single-component devices.
old-location: wdf\wdfdevicewdmassignpowerframeworksettings.htm
old-project: wdf
ms.assetid: 676A458E-A6E0-4F09-AAF2-21EA122EF74D
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WdfDeviceWdmAssignPowerFrameworkSettings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.alt-api: WdfDeviceWdmAssignPowerFrameworkSettings
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_STATE_NOTIFICATION_TYPE
req.product: Windows 10 or later.
---

# WdfDeviceWdmAssignPowerFrameworkSettings function



## -description
<p class="CCE_Message">[Applies to KMDF only]


   The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method registers  power management framework (PoFx) settings for single-component devices.



## -syntax

````
NTSTATUS WdfDeviceWdmAssignPowerFrameworkSettings(
  _In_ WDFDEVICE                      Device,
  _In_ PWDF_POWER_FRAMEWORK_SETTINGS PowerFrameworkSettings
);
````


## -parameters

### -param  Device [in]

A handle to the framework device object for which PoFx settings are being specified.


### -param PowerFrameworkSettings [in]

A pointer to a <a href="..\wdfdevice\ns-wdfdevice-_wdf_power_framework_settings.md">WDF_POWER_FRAMEWORK_SETTINGS</a> structure that describes the client driver’s PoFx settings.


## -returns
The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method returns an NTSTATUS value that indicates success or failure of the operation.
<dl>
<dt><b>STATUS_INFO_LENGTH_MISMATCH</b></dt>
</dl>The size of the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_wake_settings.md">WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS</a> structure is incorrect. 
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>The calling driver is not the device's power policy owner.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>An invalid <i>Settings</i> value is detected.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


## -remarks
The <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> method applies only to single-component devices.

After calling this method, the client driver must call <a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigns0idlesettings.md">WdfDeviceAssignS0IdleSettings</a> and set the <b>IdleTimeoutType</b> field of the <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_policy_idle_settings.md">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure to <b>SystemManagedIdleTimeout</b> or <b>SystemManagedIdleTimeoutWithHint</b>.

A driver must call <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> before or during the first time a device starts. Because a device can start more than once, for example if resource rebalancing occurs, a driver might call this method from within <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>  or  <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_init.md">EvtDeviceSelfManagedIoInit</a>. The framework calls these functions only once, even if the device is started more than once.

Alternatively, the driver could keep track of whether it has already called <b>WdfDeviceWdmAssignPowerFrameworkSettings</b>, and call it from one of the following callback functions: <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a>, <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry.md">EvtDeviceD0Entry</a>, <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled.md">EvtDeviceD0EntryPostInterruptsEnabled</a>, or <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_self_managed_io_restart.md">EvtDeviceSelfManagedIoRestart</a>.

If your driver calls <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> more than once, the framework generates a verifier error.

The power management framework (PoFx) is available only on Windows 8 and later. When running on an operating system that does not support PoFx, <b>WdfDeviceWdmAssignPowerFrameworkSettings</b> takes no action and returns STATUS_SUCCESS.

For more information, see <a href="https://msdn.microsoft.com/F96214C9-702D-402E-B873-5DF57C521B34">Supporting Functional Power States</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh406637">Overview of the Power Management Framework</a>.

In the following code example, the driver initializes a <a href="..\wdfdevice\ns-wdfdevice-_wdf_power_framework_settings.md">WDF_POWER_FRAMEWORK_SETTINGS</a> structure by calling the <a href="..\wdfdevice\nf-wdfdevice-wdf_power_framework_settings_init.md">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>  function. The driver then manually sets some of the members of the structure, and then calls <b>WdfDeviceWdmAssignPowerFrameworkSettings</b>.


## -see-also
<dl>
<dt>
<a href="..\wdfdevice\ns-wdfdevice-_wdf_power_framework_settings.md">WDF_POWER_FRAMEWORK_SETTINGS</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdf_power_framework_settings_init.md">WDF_POWER_FRAMEWORK_SETTINGS_INIT</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md">EvtDeviceWdmPrePoFxUnregisterDevice</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfDeviceWdmAssignPowerFrameworkSettings method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

