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
ms.keywords: wdf.iqueuecallbackwrite, IQueueCallbackWrite interface, IQueueCallbackWrite interface, described, IQueueCallbackWrite, wudfddi/IQueueCallbackWrite, UMDFQueueObjectRef_4abdce88-185f-4dab-823a-00da96d7d630.xml, umdf.iqueuecallbackwrite
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
-	IQueueCallbackWrite
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---

# IQueueCallbackWrite interface

<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

An I/O queue object notifies a driver when a write request is available for the driver. The I/O queue object notifies the driver when an application calls the Microsoft Win32 <b>WriteFile</b> or <b>WriteFileEx</b> function. The driver can handle the notification by registering the <b>IQueueCallbackWrite</b> interface.

## Methods

<p>The <b>IQueueCallbackWrite</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [wudfddi.IQueueCallbackWrite.OnWrite](nf-wudfddi-iqueuecallbackwrite-onwrite.md) | The OnWrite method is called to handle a write request when an application writes information to a device through the Microsoft Win32 WriteFile or WriteFileEx function. |

## Remarks

A driver registers the <b>IQueueCallbackWrite</b> interface when it calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. For more information about creating or configuring I/O queues, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">Configuring Dispatch Mode for an I/O Queue</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h |