---
UID: NN.wudfddi.IWDFFile3
title: IWDFFile3
author: windows-driver-content
description: Drivers obtain the IWDFFile3 interface by calling IWDFFile::QueryInterface.
old-location: wdf\iwdffile3.htm
ms.assetid: 67F55A00-2DE4-4ECE-8DAF-BBCBB156454E
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
req.umdf-ver: 1.11
req.alt-api: IWDFFile3
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
ms.keywords: IWDFWorkItem, GetParentObject, IWDFWorkItem::GetParentObject
req.iface: IWDFWorkItem
req.product: Windows 10 or later.
---

# IWDFFile3 interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>Drivers obtain the <b>IWDFFile3</b> interface by calling <b>IWDFFile::QueryInterface</b>.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFFile3</b> interface inherits from <a href="https://msdn.microsoft.com/library/windows/hardware/ff558915">IWDFFile2</a>. <b>IWDFFile3</b> also has these types of members:</p>

<p>The <b>IWDFFile3</b> interface has these methods.</p>

<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451279">GetInitiatorProcessId</a> method retrieves the initiator process ID associated with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface.</p>

<p> </p>

## -members
<p>The <b>IWDFFile3</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451279">GetInitiatorProcessId</a>
</td>
<td align="left" width="63%">
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451279">GetInitiatorProcessId</a> method retrieves the initiator process ID associated with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface.</p>
</td>
</tr>
</table><p>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451279">GetInitiatorProcessId</a> method retrieves the initiator process ID associated with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff558912">IWDFFile</a> interface.</p>

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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558915">IWDFFile2</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile3 interface%20 RELEASE:%20(11/2/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
