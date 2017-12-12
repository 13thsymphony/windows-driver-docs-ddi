---
UID: NN.wudfddi.IPnpCallbackRemoteInterfaceNotification
title: IPnpCallbackRemoteInterfaceNotification
author: windows-driver-content
description: A driver's IPnpCallbackRemoteInterfaceNotification interface provides a callback function that the framework calls to notify the driver when a device interface becomes available.
old-location: wdf\ipnpcallbackremoteinterfacenotification.htm
old-project: wdf
ms.assetid: 99d670dd-2358-4f1a-b111-72484bf3132c
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: __MIDL___MIDL_itf_wudfddi_0000_0000_0001, POWER_ACTION, *PPOWER_ACTION
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
req.alt-api: IPnpCallbackRemoteInterfaceNotification
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

# IPnpCallbackRemoteInterfaceNotification interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>IPnpCallbackRemoteInterfaceNotification</b> interface provides a callback function that the framework calls to notify the driver when a <a href="wdf.using_device_interfaces_in_umdf_drivers">device interface</a> becomes available.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPnpCallbackRemoteInterfaceNotification</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IPnpCallbackRemoteInterfaceNotification</b> also has these types of members:

The <b>IPnpCallbackRemoteInterfaceNotification</b> interface has these methods.

A driver's <a href="wdf.ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival">OnRemoteInterfaceArrival</a> event callback function informs the driver when a <a href="wdf.using_device_interfaces_in_umdf_drivers">device interface</a> is available. 

 


## -members
The <b>IPnpCallbackRemoteInterfaceNotification</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival">IPnpCallbackRemoteInterfaceNotification::OnRemoteInterfaceArrival</a>
</td>
<td align="left" width="63%">
A driver's <a href="wdf.ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival">OnRemoteInterfaceArrival</a> event callback function informs the driver when a <a href="wdf.using_device_interfaces_in_umdf_drivers">device interface</a> is available. 

</td>
</tr>
</table>A driver's <a href="wdf.ipnpcallbackremoteinterfacenotification_onremoteinterfacearrival">OnRemoteInterfaceArrival</a> event callback function informs the driver when a <a href="wdf.using_device_interfaces_in_umdf_drivers">device interface</a> is available. 

 


## -remarks
If your driver supports an <b>IPnpCallbackRemoteInterfaceNotification</b> interface for a device, the <b>IUnknown::QueryInterface</b> method that the driver passes to <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a> must return the interface. 


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