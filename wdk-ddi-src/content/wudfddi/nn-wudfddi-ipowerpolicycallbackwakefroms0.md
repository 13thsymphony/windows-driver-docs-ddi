---
UID: NN.wudfddi.IPowerPolicyCallbackWakeFromS0
title: IPowerPolicyCallbackWakeFromS0
author: windows-driver-content
description: A driver's IPowerPolicyCallbackWakeFromS0 interface provides callback functions that the framework calls to notify the driver about wake events.
old-location: wdf\ipowerpolicycallbackwakefroms0.htm
old-project: wdf
ms.assetid: d1b29916-9800-4276-860c-f7d143deb962
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: __MIDL___MIDL_itf_wudfddi_0000_0000_0001, *PPOWER_ACTION, POWER_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.alt-api: IPowerPolicyCallbackWakeFromS0
req.alt-loc: Wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# IPowerPolicyCallbackWakeFromS0 interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]
A driver's <b>IPowerPolicyCallbackWakeFromS0</b> interface provides callback functions that the framework calls to notify the driver about wake events. These events are related to a device's ability to wake from a low-power state while the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0).


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPowerPolicyCallbackWakeFromS0</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPowerPolicyCallbackWakeFromS0</b> also has these types of members:

The <b>IPowerPolicyCallbackWakeFromS0</b> interface has these methods.

A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_onarmwakefroms0">OnArmWakeFromS0</a> callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 

A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_ondisarmwakefroms0">OnDisarmWakeFromS0</a> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 

A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_onwakefroms0triggered">OnWakeFromS0Triggered</a> event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.

 

## -members
The <b>IPowerPolicyCallbackWakeFromS0</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.ipowerpolicycallbackwakefroms0_onarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnArmWakeFromS0</a>
</td>
<td align="left" width="63%">
A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_onarmwakefroms0">OnArmWakeFromS0</a> callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.ipowerpolicycallbackwakefroms0_ondisarmwakefroms0">IPowerPolicyCallbackWakeFromS0::OnDisarmWakeFromS0</a>
</td>
<td align="left" width="63%">
A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_ondisarmwakefroms0">OnDisarmWakeFromS0</a> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.ipowerpolicycallbackwakefroms0_onwakefroms0triggered">IPowerPolicyCallbackWakeFromS0::OnWakeFromS0Triggered</a>
</td>
<td align="left" width="63%">
A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_onwakefroms0triggered">OnWakeFromS0Triggered</a> event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.
</td>
</tr>
</table>A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_onarmwakefroms0">OnArmWakeFromS0</a> callback function arms (that is, enables) a device so that it can trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 

A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_ondisarmwakefroms0">OnDisarmWakeFromS0</a> event callback function disarms (that is, disables) a device's ability to trigger a wake signal while in a low-power device state, if the system remains in the <a href="https://msdn.microsoft.com/93ab0943-a4cc-4ef0-a250-1c63b2c915d5">system working state</a> (S0). 

A driver's <a href="wdf.ipowerpolicycallbackwakefroms0_onwakefroms0triggered">OnWakeFromS0Triggered</a> event callback function informs the driver that its device, which had previously entered a low-power device state while the system power state remained at S0, might have triggered a wake signal.

 

## -remarks
If your driver supports an <b>IPowerPolicyCallbackWakeFromS0</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a> must return the interface. 

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
</table>