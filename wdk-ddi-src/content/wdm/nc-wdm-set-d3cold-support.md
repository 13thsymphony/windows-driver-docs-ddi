---
UID: NC.wdm.SET_D3COLD_SUPPORT
title: SET_D3COLD_SUPPORT
author: windows-driver-content
description: The SetD3ColdSupport routine enables or disables transitions to the D3cold device power state.
old-location: kernel\setd3coldsupport.htm
old-project: kernel
ms.assetid: 423C621D-0AE3-468A-94A0-AA3922B410F0
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SetD3ColdSupport
req.alt-loc: Wdm.h
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
req.iface: 
req.product: Windows 10 or later.
---

# SET_D3COLD_SUPPORT callback



## -description
<p>The <i>SetD3ColdSupport</i> routine enables or disables transitions to the D3cold device power state.</p>


## -prototype

````
SET_D3COLD_SUPPORT SetD3ColdSupport;

VOID SetD3ColdSupport(
  _In_opt_ PVOID   Context,
  _In_     BOOLEAN D3ColdSupport
)
{ ... }
````


## -parameters
<dl>

### -param <i>Context</i> [in, optional]

<dd>
<p>A pointer to interface-specific context information. The caller sets this parameter to the value of the <b>Context</b> member of the <a href="..\wdm\ns-wdm--d3cold-support-interface.md">D3COLD_SUPPORT_INTERFACE</a> structure for the interface.</p>
</dd>

### -param <i>D3ColdSupport</i> [in]

<dd>
<p>Whether to allow transitions from D3hot to D3cold. Set to <b>TRUE</b> to enable these transitions. Otherwise, set to <b>FALSE.</b> For more information, see Remarks.</p>
</dd>
</dl>

## -returns
<p>None.</p>

## -remarks
<p>The driver that is the power policy owner (PPO) for a device can call this routine to enable or disable transitions to the D3cold substate that might occur when the computer is in the S0 (working) system power state and is not preparing to exit S0.</p>

<p>If a device must be able to signal a wake event from any low-power Dx state that it enters, the driver for this device should not enable transitions to the D3cold substate unless the device can signal a wake event from this substate. Otherwise, after entering D3cold, the device will be unavailable until the computer restarts or wakes from a sleeping state.</p>

<p>The driver for the device can call the <a href="..\wdm\nc-wdm-get-idle-wake-info.md">GetIdleWakeInfo</a> routine to determine whether the device can signal a wake event from D3cold.</p>

<p>If necessary, the driver for a device can make a series of <i>SetD3ColdSupport</i> calls to alternately enable and disable D3cold transitions in response to dynamically changing conditions.</p>

<p>For example, a graphics device might have a large hardware context to restore after a transition from D3cold to D0. The time required to restore this context may or may not be acceptable depending on the set of tasks that the user is currently performing. In addition, the restore time might vary with this task mix. The driver might need to dynamically enable and disable transitions to D3cold as the task mix changes.</p>

<p>A device can enter the D3cold substate only from the D3hot substate. If the driver calls <i>SetD3ColdSupport</i> to enable transitions from D3hot to D3cold, the device may or may not enter D3cold after it enters D3hot. In response to a wake event, a device might enter D0 directly from D3hot without ever passing through D3cold.</p>

<p>When a device moves from D3hot to D3cold, it probably does so because the power source that it shares with some number of other devices was turned off. Some time after these devices enter D3cold, the driver for one of the devices might request a transition to D0. In response to this request, the parent bus driver or ACPI filter driver turns on the power source, and all the devices that share the power source enter their default, power-on states.</p>

<p>The only device driver that expects this power state change is the driver that requested the change. The drivers for the other devices must receive notification of this change so that they can properly initialize their devices to operate in D0. Only a driver that can receive this notification should enable its device to enter D3cold. Otherwise, the driver will not know when the device enters D0.</p>

<p>Starting with Windows 8, a WDM driver can register its device with the power framework (PoFx) and be notified by the <a href="kernel.devicepowerrequiredcallback">DevicePowerRequiredCallback</a> routine when the device enters D0. Similarly, a KMDF driver can register its device with PoFx and be notified by the <a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-d0-entry.md">EvtDeviceD0Entry</a> event callback.</p>

<p>A driver that does not register its device with PoFx can still be notified of a transition to D0 if the device is armed for wake. When the bus drivers turn on the power to the device, they complete the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a> request. In response, the driver initializes its device to operate in D0.</p>

<p>After a power source shared by several devices turns on, the device whose driver requested the transition to D0 might be the only one of these devices that has work to do. The other devices are likely to be idle, in which case their drivers, after some time, will move these devices to D3hot.</p>

<p>If the driver calls <i>SetD3ColdSupport</i> to disable transitions to D3cold, D0 is the only device power state that the device can enter from D3hot.</p>

<p>If the driver calls <i>SetD3ColdSupport</i> to enable transitions to D3cold, these transitions might be disabled for other reasons. The driver can call the <a href="..\wdm\nc-wdm-get-d3cold-capability.md">GetD3ColdCapability</a> routine to determine whether the device is capable of entering the D3cold substate. However, a driver might not need this information. If a device is not capable of entering D3cold, calls to <i>SetD3ColdSupport</i> have no effect, but are harmless.</p>

<p>The <i>SetD3ColdSupport</i> routine affects only D3hot-to-D3cold transitions that might occur when the computer is in (and is not preparing to exit) the S0 state. This routine has no effect on the case in which the computer is preparing to exit S0 and enter a low-power system state. A device in the D3hot substate might always enter the D3cold substate just before the computer enters a system low-power state.</p>

<p>By default, before the first call to the <i>SetD3ColdSupport</i> routine, D3hot-to-D3cold transitions are disabled. To change this default so that D3hot-to-D3cold transitions are enabled before the first <i>SetD3ColdSupport</i> call, the driver package for the device can include the following two lines in the <b>DDInstall.HW</b> section of the INF file that installs the driver:</p>

<p>Windows 8 is the first version of Windows to support devices that can enter and exit the D3cold substate while the computer remains in the S0 state. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543186">Device Low-Power States</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>PASSIVE_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\ns-wdm--d3cold-support-interface.md">D3COLD_SUPPORT_INTERFACE</a>
</dt>
<dt>
<a href="kernel.devicepowerrequiredcallback">DevicePowerRequiredCallback</a>
</dt>
<dt>
<a href="..\wdfdevice\nc-wdfdevice-evt-wdf-device-d0-entry.md">EvtDeviceD0Entry</a>
</dt>
<dt>
<a href="..\wdm\nc-wdm-get-d3cold-capability.md">GetD3ColdCapability</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551766">IRP_MN_WAIT_WAKE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20SET_D3COLD_SUPPORT routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
