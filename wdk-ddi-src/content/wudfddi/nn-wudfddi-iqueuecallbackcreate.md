---
UID: NN:wudfddi.IQueueCallbackCreate
title: IQueueCallbackCreate
author: windows-driver-content
description: An I/O queue notifies a driver when an open file request is available for the driver.
old-location: wdf\iqueuecallbackcreate.htm
old-project: wdf
ms.assetid: 50b8acc6-5f08-47d5-b45d-31ff33a06be1
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: IWDFWorkItem, IWDFWorkItem::GetParentObject, GetParentObject
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
req.alt-api: IQueueCallbackCreate
req.alt-loc: wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IQueueCallbackCreate interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

An I/O queue notifies a driver when an open file request is available for the driver. The I/O queue notifies the driver in response to an application calling the Microsoft Win32 <b>CreateFile</b> function. The driver can handle the notification by registering the <b>IQueueCallbackCreate</b> interface.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackCreate</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IQueueCallbackCreate</b> also has these types of members:

The <b>IQueueCallbackCreate</b> interface has these methods.

The <a href="https://msdn.microsoft.com/f569d306-4e1e-44b7-acb0-6b46abc26b37">OnCreateFile</a> method is called to handle an open file request when an application opens a device through the Microsoft Win32 <b>CreateFile</b> function. 

 


## -members
The <b>IQueueCallbackCreate</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556841">IQueueCallbackCreate::OnCreateFile</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/f569d306-4e1e-44b7-acb0-6b46abc26b37">OnCreateFile</a> method is called to handle an open file request when an application opens a device through the Microsoft Win32 <b>CreateFile</b> function. 

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/f569d306-4e1e-44b7-acb0-6b46abc26b37">OnCreateFile</a> method is called to handle an open file request when an application opens a device through the Microsoft Win32 <b>CreateFile</b> function. 

 


## -remarks
A driver registers the <b>IQueueCallbackCreate</b> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. For more information about creating or configuring an I/O queue, see <a href="https://msdn.microsoft.com/7603c3fd-a4cb-4174-ad14-f57efedfe9de">Configuring Dispatch Mode for an I/O Queue</a>.


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