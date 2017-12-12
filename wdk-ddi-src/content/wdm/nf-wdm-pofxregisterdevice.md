---
UID: NF.wdm.PoFxRegisterDevice
title: PoFxRegisterDevice function
author: windows-driver-content
description: The PoFxRegisterDevice routine registers a device with the power management framework (PoFx).
old-location: kernel\pofxregisterdevice.htm
old-project: kernel
ms.assetid: 41A8B278-3735-41CB-B8D1-45FBF04465AD
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: PoFxRegisterDevice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PoFxRegisterDevice
req.alt-loc: Ntoskrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: Ntoskrnl.exe
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# PoFxRegisterDevice function



## -description
The <b>PoFxRegisterDevice</b> routine registers a device with the power management framework (PoFx).



## -syntax

````
NTSTATUS PoFxRegisterDevice(
  _In_  PDEVICE_OBJECT Pdo,
  _In_  PPO_FX_DEVICE  Device,
  _Out_ POHANDLE       *Handle
);
````


## -parameters

### -param Pdo [in]

A pointer to a <a href="wdkgloss.p#wdkgloss.physical_device_object__pdo_#wdkgloss.physical_device_object__pdo_">physical device object</a> (PDO). This parameter points to a <a href="kernel.device_object">DEVICE_OBJECT</a> structure that represents the physical device that is being registered. The caller is the power policy owner for the device, which is typically the device's function driver.


### -param Device [in]

A pointer to a caller-allocated <a href="kernel.po_fx_device">PO_FX_DEVICE</a> structure that contains the registration information for the device. This structure contains pointers to a set of callback routines that are implemented by the device driver. PoFx calls these routines to communicate with the driver.


### -param Handle [out]

A pointer to a location into which the routine writes a handle that represents the registration of the device with PoFx. The device driver passes this handle as an input parameter to the other <b>PoFx<i>Xxx</i></b> routines that it calls. The driver must first call <b>PoFxRegisterDevice</b> to register the device before the driver calls any other <b>PoFx<i>Xxx</i></b> routines to power-manage the device.


## -returns
<b>PoFxRegisterDevice</b> returns <b>STATUS_SUCCESS</b> if the routine successfully registers the device. Possible error return values include the following status codes.
<dl>
<dt><b><b>STATUS_INVALID_PARAMETER</b></b></dt>
</dl><i>Pdo</i> is NULL; or the <b>PPO_FX_DEVICE</b> structure has an invalid version number or a component count of zero; or the number of idle states specified for a component is zero; or the description of an idle state is invalid.
<dl>
<dt><b><b>STATUS_DEVICE_NOT_READY</b></b></dt>
</dl>The device is not ready.
<dl>
<dt><b><b>STATUS_INSUFFICIENT_RESOURCES</b></b></dt>
</dl>Insufficient resources are available to complete the registration.

 


## -remarks
A device driver typically calls this routine from the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> request handler. The driver must not call this routine before the device receives an <b>IRP_MN_START_DEVICE</b> request. The device receives the first <b>IRP_MN_START_DEVICE</b> request when the device is being started for the first time. The device receives an additional <b>IRP_MN_START_DEVICE</b> request each time the device is restarted after being stopped for resource balancing. A <b>PoFxRegisterDevice</b> call to register a device that is already registered is a fatal error and causes a bug check.

Before the driver calls <b>PoFxRegisterDevice</b>, the device must meet the following conditions:

By registering the device with PoFx, the driver assumes the responsibility for informing PoFx when a component is actively being used and when the component is idle. While the device is registered, the driver must call the <a href="kernel.pofxactivatecomponent">PoFxActivateComponent</a> routine to gain access to a component's hardware registers, and the driver must call the <a href="kernel.pofxidlecomponent">PoFxIdleComponent</a> routine to notify PoFx when the driver no longer requires access to the component.

After a driver calls <b>PoFxRegisterDevice</b> to register a device with PoFx, all components in the device are fully on and in the active condition so that the driver can finish initializing the hardware. To start active power management, the driver must call the <a href="kernel.pofxstartdevicepowermanagement">PoFxStartDevicePowerManagement</a> routine.

By default, <b>PoFxStartDevicePowerManagement</b> switches all components to the idle condition. If the driver requires a component to be in the active condition immediately after power management starts, the driver must explicitly activate the component by calling the <b>PoFxActivateComponent</b> routine, and this call must occur after the <b>PoFxRegisterDevice</b> call but before the <b>PoFxStartDevicePowerManagement</b> call.

Typically, the Kernel-Mode Driver Framework (KMDF) driver for a single-component device does not call <b>PoFxRegisterDevice</b> to register the device with PoFx. Instead, this driver receives a PoFx registration handle when KMDF calls the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a> callback function. For more information, see <a href="kmdf.supporting_multiple_functional_power_states_for_single-component_devices">Supporting Multiple Functional Power States for Single-Component Devices</a>.

For information about how the KMDF driver for a multiple-component device registers with PoFx, see <a href="kmdf.supporting_multiple_functional_power_states_for_multiple-component_devices">Supporting Multiple Functional Power States for Multiple-Component Devices</a>.


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
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.exe</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="kernel.device_object">DEVICE_OBJECT</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md">EvtDeviceWdmPostPoFxRegisterDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>
</dt>
<dt>
<a href="kernel.pofxactivatecomponent">PoFxActivateComponent</a>
</dt>
<dt>
<a href="kernel.po_fx_device">PO_FX_DEVICE</a>
</dt>
<dt>
<a href="kernel.pofxidlecomponent">PoFxIdleComponent</a>
</dt>
<dt>
<a href="kernel.pofxstartdevicepowermanagement">PoFxStartDevicePowerManagement</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PoFxRegisterDevice routine%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

