---
UID: NN:wudfddi.IWDFFile3
title: IWDFFile3
author: windows-driver-content
description: Drivers obtain the IWDFFile3 interface by calling IWDFFile::QueryInterface.
old-location: wdf\iwdffile3.htm
old-project: wdf
ms.assetid: 67F55A00-2DE4-4ECE-8DAF-BBCBB156454E
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
req.dll: WUDFx.dll
req.irql: 
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFFile3 interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

Drivers obtain the <b>IWDFFile3</b> interface by calling <b>IWDFFile::QueryInterface</b>.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFFile3</b> interface inherits from <a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a>. <b>IWDFFile3</b> also has these types of members:

The <b>IWDFFile3</b> interface has these methods.

The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451279">GetInitiatorProcessId</a> method retrieves the initiator process ID associated with an <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface.

 


## -members
The <b>IWDFFile3</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh451279">GetInitiatorProcessId</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451279">GetInitiatorProcessId</a> method retrieves the initiator process ID associated with an <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface.

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/library/windows/hardware/hh451279">GetInitiatorProcessId</a> method retrieves the initiator process ID associated with an <a href="..\wudfddi\nn-wudfddi-iwdffile.md">IWDFFile</a> interface.

 


## -remarks


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
1.11

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
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdffile2.md">IWDFFile2</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFFile3 interface%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

