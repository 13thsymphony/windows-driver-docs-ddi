---
UID: NN.wudfddi.IWDFNamedPropertyStore~r1
title: IWDFNamedPropertyStore
author: windows-driver-content
description: The IWDFNamedPropertyStore interface exposes a property-store object.
old-location: wdf\iwdfnamedpropertystore.htm
ms.assetid: f31a88c1-468f-4756-a5fa-b4aa0b8fe51d
ms.author: windowsdriverdev
ms.date: 11/2/2017
ms.topic: interface
ms.prod: windows-hardware
ms.technology: wdf
req.header: wudfddi.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.alt-api: IWDFNamedPropertyStore
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

# IWDFNamedPropertyStore interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>IWDFNamedPropertyStore</b> interface exposes a property-store object.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFNamedPropertyStore</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IWDFNamedPropertyStore</b> also has these types of members:</p>

<p>The <b>IWDFNamedPropertyStore</b> interface has these methods.</p>

<p>The <a href="https://msdn.microsoft.com/f6ebf45b-b411-4684-b430-0b17a56ec0c0">GetNameAt</a> method retrieves the name of a property.</p>

<p>The <a href="https://msdn.microsoft.com/9891e360-ca09-4ebb-8cf4-d08b3456910c">GetNameCount</a> method retrieves the number of properties in a property store.</p>

<p>The <a href="https://msdn.microsoft.com/9581e3af-f7f8-4365-8bb2-daedcb7a3280">GetNamedValue</a> method retrieves the value of a property.</p>

<p>The <a href="https://msdn.microsoft.com/1fd075c9-7d0e-4670-bac0-b7b8ba0a714f">SetNamedValue</a> method sets the value of a property.</p>

<p> </p>

## -members
<p>The <b>IWDFNamedPropertyStore</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560182">IWDFNamedPropertyStore::GetNameAt</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/f6ebf45b-b411-4684-b430-0b17a56ec0c0">GetNameAt</a> method retrieves the name of a property.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560188">IWDFNamedPropertyStore::GetNameCount</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/9891e360-ca09-4ebb-8cf4-d08b3456910c">GetNameCount</a> method retrieves the number of properties in a property store.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560190">IWDFNamedPropertyStore::GetNamedValue</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/9581e3af-f7f8-4365-8bb2-daedcb7a3280">GetNamedValue</a> method retrieves the value of a property.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff560195">IWDFNamedPropertyStore::SetNamedValue</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/1fd075c9-7d0e-4670-bac0-b7b8ba0a714f">SetNamedValue</a> method sets the value of a property.</p>
</td>
</tr>
</table><p>The <a href="https://msdn.microsoft.com/f6ebf45b-b411-4684-b430-0b17a56ec0c0">GetNameAt</a> method retrieves the name of a property.</p>

<p>The <a href="https://msdn.microsoft.com/9891e360-ca09-4ebb-8cf4-d08b3456910c">GetNameCount</a> method retrieves the number of properties in a property store.</p>

<p>The <a href="https://msdn.microsoft.com/9581e3af-f7f8-4365-8bb2-daedcb7a3280">GetNamedValue</a> method retrieves the value of a property.</p>

<p>The <a href="https://msdn.microsoft.com/1fd075c9-7d0e-4670-bac0-b7b8ba0a714f">SetNamedValue</a> method sets the value of a property.</p>

<p> </p>

## -remarks


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