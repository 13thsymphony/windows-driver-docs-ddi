---
UID: NN.wudfddi.IWDFWorkItem
title: IWDFWorkItem
author: windows-driver-content
description: This interface exposes a work item object.
old-location: wdf\iwdfworkitem.htm
old-project: wdf
ms.assetid: F9EDA26E-92E0-4936-87B7-E1E2A02A9D96
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: __MIDL___MIDL_itf_wudfddi_0000_0000_0001, POWER_ACTION, *PPOWER_ACTION
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
req.alt-api: IWDFWorkItem
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
req.product: Windows 10 or later.
---

# IWDFWorkItem interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

This interface exposes a work item object.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFWorkItem</b> interface inherits from <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>. <b>IWDFWorkItem</b> also has these types of members:

The <b>IWDFWorkItem</b> interface has these methods.


   The <a href="wdf.iwdfworkitem_enqueue">Enqueue</a> method adds this interface's framework work-item object to the system's work-item queue.
  

The <a href="wdf.iwdfworkitem_flush">Flush</a> method returns after this interface's work item has been serviced.

The <a href="wdf.iwdfworkitem_getparentobject">GetParentObject</a> method returns the parent framework object of this interface's  work item.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFWorkItem</b> interface inherits from <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>. <b>IWDFWorkItem</b> also has these types of members:

The <b>IWDFWorkItem</b> interface has these methods.


   The <a href="wdf.iwdfworkitem_enqueue">Enqueue</a> method adds this interface's framework work-item object to the system's work-item queue.
  

The <a href="wdf.iwdfworkitem_flush">Flush</a> method returns after this interface's work item has been serviced.

The <a href="wdf.iwdfworkitem_getparentobject">GetParentObject</a> method returns the parent framework object of this interface's  work item.

 


## -members
The <b>IWDFWorkItem</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfworkitem_enqueue">Enqueue</a>
</td>
<td align="left" width="63%">

   The <a href="wdf.iwdfworkitem_enqueue">Enqueue</a> method adds this interface's framework work-item object to the system's work-item queue.
  

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfworkitem_flush">Flush</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfworkitem_flush">Flush</a> method returns after this interface's work item has been serviced.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdfworkitem_getparentobject">GetParentObject</a>
</td>
<td align="left" width="63%">
The <a href="wdf.iwdfworkitem_getparentobject">GetParentObject</a> method returns the parent framework object of this interface's  work item.

</td>
</tr>
</table>
   The <a href="wdf.iwdfworkitem_enqueue">Enqueue</a> method adds this interface's framework work-item object to the system's work-item queue.
  

The <a href="wdf.iwdfworkitem_flush">Flush</a> method returns after this interface's work item has been serviced.

The <a href="wdf.iwdfworkitem_getparentobject">GetParentObject</a> method returns the parent framework object of this interface's  work item.

 


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

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFWorkItem interface%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

