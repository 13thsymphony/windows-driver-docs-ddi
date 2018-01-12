---
UID: NN:wudfddi.IWDFIoTargetStateManagement
title: IWDFIoTargetStateManagement
author: windows-driver-content
description: The IWDFIoTargetStateManagement interface exposes methods that manage and monitor the state of an I/O target object.
old-location: wdf\iwdfiotargetstatemanagement.htm
old-project: wdf
ms.assetid: 6870b6fa-1a90-4a7a-935a-4ce8eda940a1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFWorkItem, IWDFWorkItem::GetParentObject, GetParentObject
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFIoTargetStateManagement
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

# IWDFIoTargetStateManagement interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IWDFIoTargetStateManagement</b> interface exposes methods that manage and monitor the state of an I/O target object.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFIoTargetStateManagement</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWDFIoTargetStateManagement</b> also has these types of members:

The <b>IWDFIoTargetStateManagement</b> interface has these methods.

The <a href="https://msdn.microsoft.com/f915294f-457f-4913-b4b0-e94e1806a06d">GetState</a> method returns the current state of a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439492">Remove</a> method removes a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a> method starts sending queued requests to a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn927275">Stop</a> method stops sending queued requests to a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

 


## -members
The <b>IWDFIoTargetStateManagement</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559202">IWDFIoTargetStateManagement::GetState</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/f915294f-457f-4913-b4b0-e94e1806a06d">GetState</a> method returns the current state of a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559208">IWDFIoTargetStateManagement::Remove</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439492">Remove</a> method removes a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559213">IWDFIoTargetStateManagement::Start</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a> method starts sending queued requests to a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559217">IWDFIoTargetStateManagement::Stop</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/dn927275">Stop</a> method stops sending queued requests to a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/f915294f-457f-4913-b4b0-e94e1806a06d">GetState</a> method returns the current state of a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439492">Remove</a> method removes a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh973223">Start</a> method starts sending queued requests to a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn927275">Stop</a> method stops sending queued requests to a <a href="wdf.general_i_o_targets_in_umdf">local  I/O target</a>.

 


## -remarks
Drivers obtain the <b>IWDFIoTargetStateManagement</b> interface by calling <b>IWDFIoTarget::QueryInterface</b>, <b>IWDFUsbTargetPipe::QueryInterface</b>, or <b>IWDFUsbTargetPipe2::QueryInterface</b>.


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
1.5

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi.h</dt>
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