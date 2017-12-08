---
UID: NF.wdfdevice.WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
title: WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function
author: windows-driver-content
description: The WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function initializes a driver's WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS structure.
old-location: wdf\wdf_device_power_policy_idle_settings_init.htm
old-project: wdf
ms.assetid: e5a80021-1d9d-42f4-9344-9dd8d9524d0b
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
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
req.alt-api: WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT
req.alt-loc: wdfdevice.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function initializes a driver's <a href="wdf.wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.


## -syntax

````
VOID WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT(
  _Out_ PWDF_DEVICE_POWER_POLICY_IDLE_SETTINGS Settings,
  _In_  WDF_POWER_POLICY_S0_IDLE_CAPABILITIES  IdleCaps
);
````


## -parameters

### -param Settings [out]

A pointer to a driver-allocated <a href="wdf.wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure.

### -param IdleCaps [in]

A <a href="wdf.wdf_power_policy_s0_idle_capabilities">WDF_POWER_POLICY_S0_IDLE_CAPABILITIES</a>-typed enumerator.

## -returns
None

## -remarks
First, the <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b> function zeros the specified <a href="wdf.wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure and sets the structure's <b>Size</b> member. 

Then, the function sets the structure's <b>IdleTimeout</b> member to <b>IdleTimeoutDefaultValue</b>, sets the <b>UserControlOfIdleSettings</b> member to <b>IdleAllowUserControl</b>, and sets the <b>Enabled</b> member to <b>WdfUseDefault</b>. 

In addition, the function sets the <b>PowerUpIdleDeviceOnSystemWake</b> member to  <b>WdfUseDefault</b> and the <b>IdleTimeoutType</b> member to <b>DriverManagedIdleTimeout</b>.

 In addition, the function sets the <b>ExcludeD3Cold</b> member to <b>WdfUseDefault</b>.

Next, the function sets the structure's <b>IdleCaps</b> member to the value that the <i>IdleCaps</i> parameter specifies. 

Finally, if the <i>IdleCaps</i> parameter specifies <b>IdleUsbSelectiveSuspend</b> or <b>IdleCanWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceMaximum</b>. If the <i>IdleCaps</i> parameter specifies <b>IdleCannotWakeFromS0</b>, the function sets the <b>DxState</b> member to <b>PowerDeviceD3</b>.

For a code example that uses <b>WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</b>, see <a href="wdf.wdfdeviceassigns0idlesettings">WdfDeviceAssignS0IdleSettings</a>.

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
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfdevice.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdf_device_power_policy_idle_settings">WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
