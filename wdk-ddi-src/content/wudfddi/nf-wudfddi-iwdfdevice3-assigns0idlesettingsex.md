---
UID: NF.wudfddi.IWDFDevice3.AssignS0IdleSettingsEx
title: IWDFDevice3::AssignS0IdleSettingsEx
author: windows-driver-content
description: The AssignS0IdleSettingsEx method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.
old-location: wdf\iwdfdevice3_assigns0idlesettingsex.htm
old-project: wdf
ms.assetid: D020B8AA-7353-47E1-A111-82BFE6F5F03D
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: IWDFDevice3, AssignS0IdleSettingsEx, IWDFDevice3::AssignS0IdleSettingsEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.11
req.alt-api: IWDFDevice3.AssignS0IdleSettingsEx
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
req.irql: <= DISPATCH_LEVEL
req.iface: IWDFDevice3
req.product: Windows 10 or later.
---

# IWDFDevice3::AssignS0IdleSettingsEx method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The 
  <b>AssignS0IdleSettingsEx</b> method provides driver-supplied information that the framework uses when a device is idle and the system is in its working (S0) state.</p>


## -syntax

````
HRESULT AssignS0IdleSettingsEx(
  [in] PWUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS IdleSettings
);
````


## -parameters
<dl>

### -param IdleSettings [in]

<dd>
<p>A pointer to a <a href="..\wudfddi_types\ns-wudfddi-types--wudf-device-power-policy-idle-settings.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure that was initialized by a call to the <a href="..\wudfdevice\nf-wudfdevice-wudf-device-power-policy-idle-settings-init.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT</a> macro.</p>
</dd>
</dl>

## -returns
<p>The method returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.</p>

## -remarks
<p>A driver can call <b>AssignS0IdleSettingsEx</b> at any point after the driver calls <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a>. Before calling  <b>IWDFDriver::CreateDevice</b>, the driver must call <a href="wdf.iwdfdeviceinitialize_setpowerpolicyownership">IWDFDeviceInitialize::SetPowerPolicyOwnership</a> with  the <i>fTrue</i> parameter set to <b>TRUE</b>. For an example of this call sequence, see <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a>.</p>

<p>If your driver calls <b>AssignS0IdleSettingsEx</b> more than once, follow the rules described in the Remarks section of <a href="wdf.iwdfdevice2_assigns0idlesettings">AssignS0IdleSettings</a>.</p>

<p>For more information about idle power-down, see <a href="wdf.supporting_idle_power_down_in_umdf_drivers">Supporting Idle Power-Down in UMDF-based Drivers</a>.</p>

<p>The following code example initializes a <a href="..\wudfddi_types\ns-wudfddi-types--wudf-device-power-policy-idle-settings.md">WUDF_DEVICE_POWER_POLICY_IDLE_SETTINGS</a> structure and sets an idle time-out value of 10 seconds. The example then obtains the <a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a> interface and calls <b>AssignS0IdleSettingsEx</b>. </p>

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
<p>End of support</p>
</th>
<td width="70%">
<p>Unavailable in UMDF 2.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>1.11</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
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
<a href="..\wudfddi\nn-wudfddi-iwdfdevice3.md">IWDFDevice3</a>
</dt>
<dt>
<a href="..\wdfdevice\nf-wdfdevice-wdfdeviceassigns0idlesettings.md">WdfDeviceAssignS0IdleSettings</a>
</dt>
<dt>
<a href="wdf.iwdfdevice2_assigns0idlesettings">IWDFDevice2::AssignS0IdleSettings</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDevice3::AssignS0IdleSettingsEx method%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
