---
UID: NF:wudfddi.IWDFDevice2.AssignS0IdleSettings
title: IWDFDevice2::AssignS0IdleSettings method
author: windows-driver-content
description: The AssignS0IdleSettings method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.
old-location: wdf\iwdfdevice2_assigns0idlesettings.htm
old-project: wdf
ms.assetid: ffe91b9a-3b74-4dd9-b23d-096f1992485e
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFDevice2, IWDFDevice2::AssignS0IdleSettings, AssignS0IdleSettings
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IWDFDevice2.AssignS0IdleSettings
req.alt-loc: WUDFx.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFDevice2::AssignS0IdleSettings method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>AssignS0IdleSettings</b> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.



## -syntax

````
HRESULT AssignS0IdleSettings(
  [in] WDF_POWER_POLICY_S0_IDLE_CAPABILITIES IdleCaps,
  [in] DEVICE_POWER_STATE                    DxState,
  [in] ULONG                                 IdleTimeout,
  [in] WDF_POWER_POLICY_S0_IDLE_USER_CONTROL UserControlOfIdleSettings,
  [in] WDF_TRI_STATE                         Enabled
);
````


## -parameters

### -param IdleCaps [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_policy_s0_idle_capabilities.md">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator that identifies the device's ability to wake itself after it is set to a low-power state, while the system remains in its working (S0) state.


### -param DxState [in]

A <a href="..\wudfddi\ne-wudfddi-_device_power_state.md">DEVICE_POWER_STATE</a>-typed enumerator that identifies the low <a href="https://msdn.microsoft.com/2229f34c-9b88-4e3e-802e-f7be2c7ef168">device power state</a> that the device will enter after the idle timeout period ends. DEVICE_POWER_STATE values are defined in wdm.h.


### -param IdleTimeout [in]

The amount of time, in milliseconds, that the device will remain idle before the framework places it in the <i>DxState</i>-supplied low-power state. To use the framework's default idle timeout value, specify <b>IdleTimeoutDefaultValue</b> For more information, see the Remarks section.


### -param UserControlOfIdleSettings [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_power_policy_s0_idle_user_control.md">WDF_POWER_POLICY_S0_IDLE_USER_CONTROL</a>-typed enumerator that indicates whether users have the ability to modify the device's idle settings.


### -param Enabled [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_tri_state.md">WDF_TRI_STATE</a>-typed enumerator that indicates whether the device will be powered down if it remains idle and while the system power is at S0. This member can have one of the following values:

<dl>
<dd>
<b>WdfTrue</b> - Powering down is enabled.

</dd>
<dd>
<b>WdfFalse</b> - Powering down is disabled.

</dd>
<dd>
<b>WdfUseDefault</b> - Powering down is initially enabled by default; but if the <i>UserControlOfIdleSettings</i> parameter is set to <b>IdleAllowUserControl</b>, the <a href="wdf.user_control_of_device_idle_and_wake_behavior">user's setting or driver's INF file</a> overrides the initial value.

</dd>
</dl>
If powering down is enabled, the device has a wake-up capability, and the idle timeout value expires, the framework calls the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556817">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a> callback function before the device enters a low-power state.


## -returns
<b>AssignS0IdleSettings</b> returns S_OK if the operation succeeds. Otherwise, the method might return one of the following values:
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>The caller specified an invalid value for an input parameter.
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_INVALID_DEVICE_REQUEST)</b></dt>
</dl>The calling driver is not the device's <a href="wdf.power_policy_ownership_in_umdf">power policy owner</a>.
<dl>
<dt><b>HRESULT_FROM_NT(STATUS_POWER_STATE_INVALID)</b></dt>
</dl>The <i>DxState</i> parameter specifies an invalid device power state, or the <i>IdleCaps</i> parameter indicates the device can wake itself, but the bus driver indicates the device cannot wake itself.

 

This method might return one of the other values that Winerror.h contains.


## -remarks
The first time a driver calls <b>AssignS0IdleSettings</b>, the following actions occur:

The framework stores the values of all parameters. 

If the <i>UserControlOfIdleSettings</i> parameter is set to <b>IdleAllowUserControl</b> and if the <i>Enabled</i> parameter is set to <b>WdfUseDefault</b>, the framework reads the registry to find out if the user has enabled powering down the device when it is idle.

During subsequent calls to <b>AssignS0IdleSettings</b>, the framework only stores the values of the <i>DxState</i>, <i>IdleTimeout</i>, and <i>Enabled</i> parameters. Also, the framework stores the value of the <i>IdleCaps</i> parameter subject to the following rules:


<ul>
<li>
If the driver has ever specified <b>IdleCanWakeFromS0</b> for the <i>IdleCaps</i> parameter's value in a previous call to <b>AssignS0IdleSettings</b>, it cannot subsequently change that value to <b>IdleUsbSelectiveSuspend</b>.

</li>
<li>
If the driver has ever specified <b>IdleUsbSelectiveSuspend</b> for the <i>IdleCaps</i> parameter's value in a previous call to <b>AssignS0IdleSettings</b>, it cannot subsequently change that value to <b>IdleCanWakeFromS0</b>.

</li>
</ul>


If the driver has ever specified <b>IdleCanWakeFromS0</b> for the <i>IdleCaps</i> parameter's value in a previous call to <b>AssignS0IdleSettings</b>, it cannot subsequently change that value to <b>IdleUsbSelectiveSuspend</b>.

If the driver has ever specified <b>IdleUsbSelectiveSuspend</b> for the <i>IdleCaps</i> parameter's value in a previous call to <b>AssignS0IdleSettings</b>, it cannot subsequently change that value to <b>IdleCanWakeFromS0</b>.

The following rules apply to the value that you specify for the <i>DxState</i> parameter:

The value cannot be <b>PowerDeviceD0</b>. 

For USB devices, the value cannot be <b>PowerDeviceD0</b> or <b>PowerDeviceD3</b>.

If you specify <b>DevicePowerMaximum</b>, the framework uses the value that the kernel-mode driver for the device's bus supplied in the <b>DeviceWake</b> member of its <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a> structure. 

If the value of the <i>IdleCaps</i> parameter is <b>IdleCanWakeFromS0</b> or <b>IdleUsbSelectiveSuspend</b>, you cannot specify a device power state that is lower than the device power state in the <b>DeviceWake</b> member of the kernel-mode bus driver's <a href="..\wdfdevice\ns-wdfdevice-_wdf_device_power_capabilities.md">WDF_DEVICE_POWER_CAPABILITIES</a> structure. (In other words, if the bus driver's <b>DeviceWake</b> value is <b>PowerDeviceD2</b>, your function driver's <i>DxState</i> value cannot be <b>PowerDeviceD3</b>.) 

If you specify <b>IdleTimeoutDefaultValue</b> for the <i>IdleTimeout</i> parameter, the timeout defaults to five seconds. You can examine the output from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff566199">!wudfext.wudfdevice</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff566191">!wudfext.umdevstacks</a> debugger extensions to see the effective settings and power references.

For information about registry entries that control a device's idle capabilities, see <a href="https://msdn.microsoft.com/9341c412-dd0a-4e80-a164-250e24004082">User Control of Device Idle and Wake Behavior in UMDF</a>. 

For more information about supporting a device's idle capabilities, see <a href="wdf.supporting_idle_power_down_in_umdf_drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.

The following code example is based on the UMDF version of the toaster sample. The example obtains the <a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a> interface and then calls <b>AssignS0IdleSettings</b>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
End of support

</th>
<td width="70%">
Unavailable in UMDF 2.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version

</th>
<td width="70%">
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>WUDFx.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfdevice2.md">IWDFDevice2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556923">IWDFDevice2::AssignSxWakeSettings</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/D020B8AA-7353-47E1-A111-82BFE6F5F03D">IWDFDevice3::AssignS0IdleSettingsEx</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice2::AssignS0IdleSettings method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

