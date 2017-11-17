---
UID: NN.wudfddi.IObjectCleanup
title: IObjectCleanup
author: windows-driver-content
description: Any driver that stores a reference-counted COM interface to a WDF object must support the IObjectCleanup interface to prevent interface leakage. Note that drivers, in general, are not required to hold references to WDF objects.
old-location: wdf\iobjectcleanup.htm
ms.assetid: 5e465c90-3290-4c89-bf47-521280c0fe5c
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
req.alt-api: IObjectCleanup
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

# IObjectCleanup interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>Any driver that stores a reference-counted COM interface to a WDF object must support the <b>IObjectCleanup</b> interface to prevent interface leakage. Note that drivers, in general, are not required to hold references to WDF objects.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IObjectCleanup</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IObjectCleanup</b> also has these types of members:</p>

<p>The <b>IObjectCleanup</b> interface has these methods.</p>

<p>The <a href="https://msdn.microsoft.com/6b66c496-d1cc-4b7a-ae50-f18fffa7275a">OnCleanup</a> method releases any references to a WDF object to prevent interface leakage.</p>

<p> </p>

## -members
<p>The <b>IObjectCleanup</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556760">IObjectCleanup::OnCleanup</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/6b66c496-d1cc-4b7a-ae50-f18fffa7275a">OnCleanup</a> method releases any references to a WDF object to prevent interface leakage.</p>
</td>
</tr>
</table><p>The <a href="https://msdn.microsoft.com/6b66c496-d1cc-4b7a-ae50-f18fffa7275a">OnCleanup</a> method releases any references to a WDF object to prevent interface leakage.</p>

<p> </p>

## -remarks
<p>The framework calls the method of the <b>IObjectCleanup</b> interface when the associated framework object is about to be released.</p>

<p>A driver can register the <b>IObjectCleanup</b> interface when the driver calls any method that creates a WDF object. </p>

<p>The framework calls the method of the <b>IObjectCleanup</b> interface when the associated framework object is about to be released.</p>

<p>A driver can register the <b>IObjectCleanup</b> interface when the driver calls any method that creates a WDF object. </p>

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