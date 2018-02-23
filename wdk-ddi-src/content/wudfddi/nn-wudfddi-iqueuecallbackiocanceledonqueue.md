---
UID: NN:wudfddi.IQueueCallbackIoCanceledOnQueue
title: IQueueCallbackIoCanceledOnQueue
author: windows-driver-content
description: The IQueueCallbackIoCanceledOnQueue interface is optional. Your driver can provide this interface if you want UMDF to notify the driver when an I/O request is canceled while it is in the driver's I/O queue.
old-location: wdf\iqueuecallbackiocanceledonqueue.htm
old-project: wdf
ms.assetid: d85b5c70-4e03-4a12-bc0b-e738d4dab6cf
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.iqueuecallbackiocanceledonqueue, IQueueCallbackIoCanceledOnQueue interface, IQueueCallbackIoCanceledOnQueue interface, described, IQueueCallbackIoCanceledOnQueue, wudfddi/IQueueCallbackIoCanceledOnQueue, UMDFQueueObjectRef_65c767dc-7b2b-4b25-a546-d0f3fb6fba14.xml, umdf.iqueuecallbackiocanceledonqueue
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: WUDFx.dll
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	wudfddi.h
apiname:
-	IQueueCallbackIoCanceledOnQueue
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IQueueCallbackIoCanceledOnQueue interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>IQueueCallbackIoCanceledOnQueue</b> interface is optional. Your driver can provide this interface if you want UMDF to notify the driver when an I/O request is canceled while it is in the driver's I/O queue.

## Methods

<p>The <b>IQueueCallbackIoCanceledOnQueue</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IQueueCallbackIoCanceledOnQueue.OnIoCanceledOnQueue](nf-wudfddi-iqueuecallbackiocanceledonqueue-oniocanceledonqueue.md) | A driver's OnIoCanceledOnQueue event callback function informs the driver that an I/O request was canceled while it was in an I/O queue. |

## Remarks

To register an <b>IQueueCallbackIoCanceledOnQueue</b> interface for an I/O queue, the driver must provide a <b>QueryInterface</b> function for the I/O queue object. The <b>QueryInterface</b> function must return a pointer to the <b>IQueueCallbackIoCanceledOnQueue</b> interface. UMDF calls the <b>QueryInterface</b> method of the <b>IUnknown</b> interface that the driver passes to <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h |