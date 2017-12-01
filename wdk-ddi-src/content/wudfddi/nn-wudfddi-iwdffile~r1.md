---
UID: NN.wudfddi.IWDFFile~r1
title: IWDFFile
author: windows-driver-content
description: The IWDFFile interface exposes the file object that represents the HANDLE that is returned by the Microsoft Win32 CreateFile function.
old-location: wdf\iwdffile.htm
old-project: wdf
ms.assetid: bf8e5ab1-9a17-4eb5-8c54-34670ea27068
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IWDFWorkItem, GetParentObject, IWDFWorkItem::GetParentObject
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
req.alt-api: IWDFFile
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
req.iface: IWDFWorkItem
req.product: Windows 10 or later.
---

# IWDFFile interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <a href="..\wudfddi\nn-wudfddi-iwdffilehandletargetfactory.md">IWDFFile</a> interface exposes the file object that represents the HANDLE that is returned by the Microsoft Win32 <b>CreateFile</b> function. All further operations on this handle, such as calls to the Win32 <b>ReadFile</b> function and the <b>DeviceIoControl</b> function, are sent to this file object.</p>


## -inheritance
<p>The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IWDFFile</b> interface inherits from <a href="..\wudfddi\nn-wudfddi-iwdfobject.md">IWDFObject</a>. <b>IWDFFile</b> also has these types of members:</p>

<p>The <b>IWDFFile</b> interface has these methods.</p>

<p>The <a href="wdf.iwdffile_getdevice">GetDevice</a> method returns the interface to the device object that a file object is associated with.</p>

<p>The <a href="wdf.iwdffile_retrievefilename">RetrieveFileName</a> method retrieves the full name of the file that is associated with the underlying kernel-mode device.</p>

<p> </p>

## -members
<p>The <b>IWDFFile</b> interface has these methods.</p><table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdffile_getdevice">IWDFFile::GetDevice</a>
</td>
<td align="left" width="63%">
<p>The <a href="wdf.iwdffile_getdevice">GetDevice</a> method returns the interface to the device object that a file object is associated with.</p>
</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.iwdffile_retrievefilename">IWDFFile::RetrieveFileName</a>
</td>
<td align="left" width="63%">
<p>The <a href="wdf.iwdffile_retrievefilename">RetrieveFileName</a> method retrieves the full name of the file that is associated with the underlying kernel-mode device.</p>
</td>
</tr>
</table><p>The <a href="wdf.iwdffile_getdevice">GetDevice</a> method returns the interface to the device object that a file object is associated with.</p>

<p>The <a href="wdf.iwdffile_retrievefilename">RetrieveFileName</a> method retrieves the full name of the file that is associated with the underlying kernel-mode device.</p>

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