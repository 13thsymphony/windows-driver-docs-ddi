---
UID: NN.wudfddi.IDriverEntry
title: IDriverEntry
author: windows-driver-content
description: The IDriverEntry interface exposes the user-mode driver's main entry and exit points.
old-location: wdf\idriverentry.htm
ms.assetid: eae6f032-2f31-43e1-9ac0-38ccc4840580
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: interface
ms.prod: windows-hardware
ms.technology: wdf
req.header: wudfddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IDriverEntry
req.alt-loc: Wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
ms.keywords: IWDFWorkItem, GetParentObject, IWDFWorkItem::GetParentObject
req.iface: IWDFWorkItem
req.product: Windows 10 or later.
---

# IDriverEntry interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>IDriverEntry</b> interface exposes the user-mode driver's main entry and exit points.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IDriverEntry</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IDriverEntry</b> also has these types of members:</p>

<p>The <b>IDriverEntry</b> interface has these methods.</p>

<p>The <a href="https://msdn.microsoft.com/9366029e-4f8b-4121-ad99-01a5116a7f46">OnDeinitialize</a> method performs any operations that are necessary before a system unloads a driver.</p>

<p>The <a href="https://msdn.microsoft.com/f2953b0d-6745-4804-bcda-47c7ddfb901f">OnDeviceAdd</a> method adds a new device to a system.</p>

<p>The <a href="https://msdn.microsoft.com/c676588e-348b-4840-9873-6b1bb2454987">OnInitialize</a> method performs any operations that are necessary to initialize a driver.</p>

<p> </p>

## -members
<p>The <b>IDriverEntry</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554890">IDriverEntry::OnDeinitialize</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/9366029e-4f8b-4121-ad99-01a5116a7f46">OnDeinitialize</a> method performs any operations that are necessary before a system unloads a driver.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554896">IDriverEntry::OnDeviceAdd</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/f2953b0d-6745-4804-bcda-47c7ddfb901f">OnDeviceAdd</a> method adds a new device to a system.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554900">IDriverEntry::OnInitialize</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/c676588e-348b-4840-9873-6b1bb2454987">OnInitialize</a> method performs any operations that are necessary to initialize a driver.</p>
</td>
</tr>
</table><p>The <a href="https://msdn.microsoft.com/9366029e-4f8b-4121-ad99-01a5116a7f46">OnDeinitialize</a> method performs any operations that are necessary before a system unloads a driver.</p>

<p>The <a href="https://msdn.microsoft.com/f2953b0d-6745-4804-bcda-47c7ddfb901f">OnDeviceAdd</a> method adds a new device to a system.</p>

<p>The <a href="https://msdn.microsoft.com/c676588e-348b-4840-9873-6b1bb2454987">OnInitialize</a> method performs any operations that are necessary to initialize a driver.</p>

<p> </p>

## -remarks


## -requirements
<table>
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
</table>