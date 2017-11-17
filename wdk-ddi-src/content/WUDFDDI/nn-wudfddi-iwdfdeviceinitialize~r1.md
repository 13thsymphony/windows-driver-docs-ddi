---
UID: NN.wudfddi.IWDFDeviceInitialize~r1
title: IWDFDeviceInitialize
author: windows-driver-content
description: The IWDFDeviceInitialize interface is a helper interface that the framework supplies as an input parameter to the driver's IDriverEntry::OnDeviceAdd method.
old-location: wdf\iwdfdeviceinitialize.htm
ms.assetid: a776069c-0cbb-4ae9-bf6b-1d300dbcec34
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: interface
ms.prod: windows-hardware
ms.technology: wdf
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFDeviceInitialize
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
ms.keywords: IWDFWorkItem, GetParentObject, IWDFWorkItem::GetParentObject
req.iface: IWDFWorkItem
req.product: Windows 10 or later.
---

# IWDFDeviceInitialize interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>IWDFDeviceInitialize</b> interface is a helper interface that the framework supplies as an input parameter to the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff554896">IDriverEntry::OnDeviceAdd</a> method.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFDeviceInitialize</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWDFDeviceInitialize</b> also has these types of members:</p>

<p>The <b>IWDFDeviceInitialize</b> interface has these methods.</p>

<p>The <a href="https://msdn.microsoft.com/b9c8e54e-7cd5-48a9-b948-5327900c8a99">AutoForwardCreateCleanupClose</a> method controls when create, cleanup, and close notifications are forwarded to the next lower driver in the device stack.</p>

<p>The <a href="https://msdn.microsoft.com/64f15528-e934-4bdd-a9f7-6790eef7c7c5">GetPnpCapability</a> method determines the state of the specified  Plug and Play (PnP) capability.</p>

<p>The <a href="https://msdn.microsoft.com/224277b4-447f-4981-aabf-90a10322c0df">RetrieveDeviceInstanceId</a> method retrieves the identifier of an instance of a device.</p>

<p>The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a device property store that clients can read and write device properties through.</p>

<p>The <a href="https://msdn.microsoft.com/a5f61a83-43db-4ad7-9b18-0cdf574ea546">SetFilter</a> method sets the property that enables a device as a filter device.</p>

<p>The <a href="https://msdn.microsoft.com/c0062ad4-6666-49db-9d53-70f2ed2353d1">SetLockingConstraint</a> method sets the synchronization (or locking) model for callback functions into the driver.</p>

<p>The <a href="https://msdn.microsoft.com/82892740-12f6-469b-a65c-6905d32c0b0d">SetPnpCapability</a> method sets the specified Plug and Play (PnP) capability of a device to the specified state.</p>

<p>The <a href="https://msdn.microsoft.com/18b0b277-97c8-4aff-9f09-34822ce84290">SetPowerPolicyOwnership</a> method sets the ownership of the power policy to a driver or removes ownership from the driver.</p>

<p> </p>

## -members
<p>The <b>IWDFDeviceInitialize</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556971">IWDFDeviceInitialize::AutoForwardCreateCleanupClose</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/b9c8e54e-7cd5-48a9-b948-5327900c8a99">AutoForwardCreateCleanupClose</a> method controls when create, cleanup, and close notifications are forwarded to the next lower driver in the device stack.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556974">IWDFDeviceInitialize::GetPnpCapability</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/64f15528-e934-4bdd-a9f7-6790eef7c7c5">GetPnpCapability</a> method determines the state of the specified  Plug and Play (PnP) capability.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556980">IWDFDeviceInitialize::RetrieveDeviceInstanceId</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/224277b4-447f-4981-aabf-90a10322c0df">RetrieveDeviceInstanceId</a> method retrieves the identifier of an instance of a device.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556982">IWDFDeviceInitialize::RetrieveDevicePropertyStore</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a device property store that clients can read and write device properties through.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556985">IWDFDeviceInitialize::SetFilter</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/a5f61a83-43db-4ad7-9b18-0cdf574ea546">SetFilter</a> method sets the property that enables a device as a filter device.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556991">IWDFDeviceInitialize::SetLockingConstraint</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/c0062ad4-6666-49db-9d53-70f2ed2353d1">SetLockingConstraint</a> method sets the synchronization (or locking) model for callback functions into the driver.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556993">IWDFDeviceInitialize::SetPnpCapability</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/82892740-12f6-469b-a65c-6905d32c0b0d">SetPnpCapability</a> method sets the specified Plug and Play (PnP) capability of a device to the specified state.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557001">IWDFDeviceInitialize::SetPowerPolicyOwnership</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/18b0b277-97c8-4aff-9f09-34822ce84290">SetPowerPolicyOwnership</a> method sets the ownership of the power policy to a driver or removes ownership from the driver.</p>
</td>
</tr>
</table><p>The <a href="https://msdn.microsoft.com/b9c8e54e-7cd5-48a9-b948-5327900c8a99">AutoForwardCreateCleanupClose</a> method controls when create, cleanup, and close notifications are forwarded to the next lower driver in the device stack.</p>

<p>The <a href="https://msdn.microsoft.com/64f15528-e934-4bdd-a9f7-6790eef7c7c5">GetPnpCapability</a> method determines the state of the specified  Plug and Play (PnP) capability.</p>

<p>The <a href="https://msdn.microsoft.com/224277b4-447f-4981-aabf-90a10322c0df">RetrieveDeviceInstanceId</a> method retrieves the identifier of an instance of a device.</p>

<p>The <a href="https://msdn.microsoft.com/be47a1f0-03ff-432c-a3ef-5978c9b48183">RetrieveDevicePropertyStore</a> method retrieves a device property store that clients can read and write device properties through.</p>

<p>The <a href="https://msdn.microsoft.com/a5f61a83-43db-4ad7-9b18-0cdf574ea546">SetFilter</a> method sets the property that enables a device as a filter device.</p>

<p>The <a href="https://msdn.microsoft.com/c0062ad4-6666-49db-9d53-70f2ed2353d1">SetLockingConstraint</a> method sets the synchronization (or locking) model for callback functions into the driver.</p>

<p>The <a href="https://msdn.microsoft.com/82892740-12f6-469b-a65c-6905d32c0b0d">SetPnpCapability</a> method sets the specified Plug and Play (PnP) capability of a device to the specified state.</p>

<p>The <a href="https://msdn.microsoft.com/18b0b277-97c8-4aff-9f09-34822ce84290">SetPowerPolicyOwnership</a> method sets the ownership of the power policy to a driver or removes ownership from the driver.</p>

<p> </p>

## -remarks
<p> The driver calls the methods of this interface to set the properties for a new device object and passes this interface as an input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create the new device object.</p>

<p>Do not use  this interface after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.</p>

<p> The driver calls the methods of this interface to set the properties for a new device object and passes this interface as an input to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a> method to create the new device object.</p>

<p>Do not use  this interface after calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff558899">IWDFDriver::CreateDevice</a>.</p>

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