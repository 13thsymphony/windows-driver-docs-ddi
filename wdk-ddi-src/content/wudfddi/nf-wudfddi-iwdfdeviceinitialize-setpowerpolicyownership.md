---
UID: NF.wudfddi.IWDFDeviceInitialize.SetPowerPolicyOwnership
title: IWDFDeviceInitialize::SetPowerPolicyOwnership
author: windows-driver-content
description: The SetPowerPolicyOwnership method sets the ownership of the power policy to a driver or removes ownership from the driver.
old-location: wdf\iwdfdeviceinitialize_setpowerpolicyownership.htm
old-project: wdf
ms.assetid: 18b0b277-97c8-4aff-9f09-34822ce84290
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: IWDFDeviceInitialize, SetPowerPolicyOwnership, IWDFDeviceInitialize::SetPowerPolicyOwnership
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFDeviceInitialize.SetPowerPolicyOwnership
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
req.iface: IWDFDeviceInitialize
req.product: Windows 10 or later.
---

# IWDFDeviceInitialize::SetPowerPolicyOwnership method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>SetPowerPolicyOwnership</b> method sets the ownership of the power policy to a driver or removes ownership from the driver.</p>


## -syntax

````
void SetPowerPolicyOwnership(
  [in] BOOL fTrue
);
````


## -parameters
<dl>

### -param <i>fTrue</i> [in]

<dd>
<p>A BOOL value that specifies whether to set power-policy ownership to the driver or remove ownership from the driver. <b>TRUE</b> indicates to set power-policy ownership to the driver; <b>FALSE</b> indicates to remove ownership from the driver.</p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>By default, UMDF drivers are not registered as power-policy owners for their device stack. To register itself as the power-policy owner for its device stack, a UMDF driver must explicitly call <b>SetPowerPolicyOwnership</b> and pass <b>TRUE</b> to the <i>fTrue</i> parameter in this call.</p>

<p>For more information, see <a href="wdf.power_policy_ownership_in_umdf">Power Policy Ownership in UMDF</a>.</p>

<p>For a code example of how to use the <b>SetPowerPolicyOwnership</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.</p>

<p>By default, UMDF drivers are not registered as power-policy owners for their device stack. To register itself as the power-policy owner for its device stack, a UMDF driver must explicitly call <b>SetPowerPolicyOwnership</b> and pass <b>TRUE</b> to the <i>fTrue</i> parameter in this call.</p>

<p>For more information, see <a href="wdf.power_policy_ownership_in_umdf">Power Policy Ownership in UMDF</a>.</p>

<p>For a code example of how to use the <b>SetPowerPolicyOwnership</b> method, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.</p>

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
<p>1.5</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556965">IWDFDeviceInitialize</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFDeviceInitialize::SetPowerPolicyOwnership method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
