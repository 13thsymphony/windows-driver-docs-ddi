---
UID: NN.wudfddi.IFileCallbackClose
title: IFileCallbackClose
author: windows-driver-content
description: The framework can notify a driver when the driver should perform a close operation. The driver can handle the notification by registering the IFileCallbackClose interface.
old-location: wdf\ifilecallbackclose.htm
old-project: wdf
ms.assetid: 22ecfb7b-daba-4321-bca5-4460ead8e3cd
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: __MIDL___MIDL_itf_wudfddi_0000_0000_0001, *PPOWER_ACTION, POWER_ACTION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: wudfddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IFileCallbackClose
req.alt-loc: wudfddi.h
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
req.product: Windows 10 or later.
---

# IFileCallbackClose interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]
The framework can notify a driver when the driver should perform a close operation.  The driver can handle the notification by registering the <b>IFileCallbackClose</b> interface.
A driver registers the <b>IFileCallbackClose</b> interface when it calls the <a href="wdf.iwdfdriver_createdevice">IWDFDriver::CreateDevice</a> method to create a device object. 


## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IFileCallbackClose</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IFileCallbackClose</b> also has these types of members:

The <b>IFileCallbackClose</b> interface has these methods.

The <a href="wdf.ifilecallbackclose_onclosefile">OnCloseFile</a> method is called when the last reference count on a file object goes down to zero and before the file object is released. 

 

## -members
The <b>IFileCallbackClose</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="wdf.ifilecallbackclose_onclosefile">IFileCallbackClose::OnCloseFile</a>
</td>
<td align="left" width="63%">
The <a href="wdf.ifilecallbackclose_onclosefile">OnCloseFile</a> method is called when the last reference count on a file object goes down to zero and before the file object is released. 
</td>
</tr>
</table>The <a href="wdf.ifilecallbackclose_onclosefile">OnCloseFile</a> method is called when the last reference count on a file object goes down to zero and before the file object is released. 

 

## -remarks


## -requirements
<table>
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