---
UID: NN:wudfddi.IQueueCallbackWrite
title: IQueueCallbackWrite
author: windows-driver-content
description: An I/O queue object notifies a driver when a write request is available for the driver.
old-location: wdf\iqueuecallbackwrite.htm
old-project: wdf
ms.assetid: 8b44e1e1-c648-4eec-bb3e-ab327dc08f98
ms.author: windowsdriverdev
ms.date: 1/11/2018
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
req.alt-api: IQueueCallbackWrite
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

# IQueueCallbackWrite interface



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

An I/O queue object notifies a driver when a write request is available for the driver. The I/O queue object notifies the driver when an application calls the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. The driver can handle the notification by registering the <b>IQueueCallbackWrite</b> interface.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IQueueCallbackWrite</b> interface inherits from the <a href="com.iunknown" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IUnknown</b></a> interface. <b>IQueueCallbackWrite</b> also has these types of members:

The <b>IQueueCallbackWrite</b> interface has these methods.

The <a href="https://msdn.microsoft.com/a87a9976-f844-4e69-82d3-2d426e359763">OnWrite</a> method is called to handle a write request when an application writes information to a device through the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. 

 


## -members
The <b>IQueueCallbackWrite</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff556885">IQueueCallbackWrite::OnWrite</a>
</td>
<td align="left" width="63%">
The <a href="https://msdn.microsoft.com/a87a9976-f844-4e69-82d3-2d426e359763">OnWrite</a> method is called to handle a write request when an application writes information to a device through the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. 

</td>
</tr>
</table>The <a href="https://msdn.microsoft.com/a87a9976-f844-4e69-82d3-2d426e359763">OnWrite</a> method is called to handle a write request when an application writes information to a device through the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. 

 


## -remarks
A driver registers the <b>IQueueCallbackWrite</b> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. For more information about creating or configuring I/O queues, see <a href="https://msdn.microsoft.com/7603c3fd-a4cb-4174-ad14-f57efedfe9de">Configuring Dispatch Mode for an I/O Queue</a>.</p>