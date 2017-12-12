---
UID: NN.printerextension.IPrinterQueue2
title: IPrinterQueue2
author: windows-driver-content
description: Represents a single printer queue.
old-location: print\iprinterqueue2.htm
old-project: print
ms.assetid: 06459A1F-A14B-43BA-9771-47205CC3F388
ms.author: windowsdriverdev
ms.date: 12/9/2017
ms.keywords: tagPrintSchemaSelectionType, PrintSchemaSelectionType
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterQueue2
req.alt-loc: Printerextension.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.product: Windows 10 or later.
---

# IPrinterQueue2 interface



## -description
Represents a single printer queue. 

This interface extends <a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a> and allows a user to manage print jobs and device maintenance from within a UWP  device app for printers, or from a printer extension.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueue2</b> interface inherits from <a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>. <b>IPrinterQueue2</b> also has these types of members:

The <b>IPrinterQueue2</b> interface has these methods.

Retrieves an <a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a> object, and initializes the object with the range of jobs to be monitored.

Uses an XML string value to send a Bidi Set request as an asynchronous operation.

 


## -members
The <b>IPrinterQueue2</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprinterqueue2_getprinterqueueview">GetPrinterQueueView</a>
</td>
<td align="left" width="63%">
Retrieves an <a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a> object, and initializes the object with the range of jobs to be monitored.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprinterqueue2_sendbidisetrequestasync">SendBidiSetRequestAsync</a>
</td>
<td align="left" width="63%">
Uses an XML string value to send a Bidi Set request as an asynchronous operation.

</td>
</tr>
</table>Retrieves an <a href="..\printerextension\nn-printerextension-iprinterqueueview.md">IPrinterQueueView</a> object, and initializes the object with the range of jobs to be monitored.

Uses an XML string value to send a Bidi Set request as an asynchronous operation.

 


## -remarks
<b>IPrinterQueue2</b> also helps to make it possible to perform device maintenance and job management from a UWP  device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a> and <a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Printerextension.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/310E92A9-F751-4346-9B2D-0578A136AD20">Device Maintenance</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue2 interface%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

