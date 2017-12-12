---
UID: NN.printerextension.IPrinterQueueView
title: IPrinterQueueView
author: windows-driver-content
description: Provides a way to change the range of print jobs being monitored.
old-location: print\iprinterqueueview.htm
old-project: print
ms.assetid: 81B3D4A3-7176-4656-B23D-04F0F84D9000
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
req.alt-api: IPrinterQueueView
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

# IPrinterQueueView interface



## -description
Provides a way to change the range of print jobs being monitored.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueueView</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IDispatch</b></a> interface. <b>IPrinterQueueView</b> also has these types of members:

The <b>IPrinterQueueView</b> interface has these methods.

Sets the range of print jobs being monitored.

 


## -members
The <b>IPrinterQueueView</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="print.iprinterqueueview_setviewrange">SetViewRange</a>
</td>
<td align="left" width="63%">
Sets the range of print jobs being monitored.

</td>
</tr>
</table>Sets the range of print jobs being monitored.

 


## -remarks
An event is raised whenever the status of the print queue changes. So when a client uses <a href="print.iprinterqueueview_setviewrange">SetViewRange</a> to specify the range of print jobs (the view) to be monitored, the <a href="print.iprinterqueueviewevent_onchanged">IPrinterQueueViewEvent::OnChanged</a> event method fires, and the live queue is returned in response.

And also, note that job enumeration starts when the first event handler is added and stops when the last event handler is removed.

<b>IPrinterQueueView</b> also helps to make it possible to perform job management from a UWP  device app or from a printer extension. For more information, see <a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>.


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
<a href="print.iprinterqueueviewevent_onchanged">IPrinterQueueViewEvent::OnChanged</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/D1236DD2-D4AD-4615-9036-7EC75D6CADCE">Job Management</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueueView interface%20 RELEASE:%20(12/9/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

