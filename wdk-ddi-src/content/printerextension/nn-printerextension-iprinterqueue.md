---
UID: NN:printerextension.IPrinterQueue
title: IPrinterQueue
author: windows-driver-content
description: Represents a single printer queue.
old-location: print\iprinterqueue_interface.htm
old-project: print
ms.assetid: 2DB57234-E783-4C6B-A743-F1E9F7D34D97
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: IPrintSchemaTicket2, IPrintSchemaTicket2::GetParameterInitializer, GetParameterInitializer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: interface
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrinterQueue
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
req.irql: 
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---

# IPrinterQueue interface



## -description
Represents a single printer queue.



## -inheritance
The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueue</b> interface inherits from the <a href="ebbff4bc-36b2-4861-9efa-ffa45e013eb5" xmlns:loc="http://microsoft.com/wdcml/l10n"><b>IDispatch</b></a> interface. <b>IPrinterQueue</b> also has these types of members:

The <b>IPrinterQueue</b> interface has these methods.

Gets the properties in the property bag for the queue.

Performs an asynchronous refresh operation with the specified query, and invokes the <a href="https://msdn.microsoft.com/D0CD9950-DF73-4D46-B901-FA45BA88D3CF">IPrinterQueueEvent::OnBidiResponseReceived</a> method.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueue</b> interface has these properties.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh973215">Handle</a>


Read-only

Gets the underlying native handle for this print queue.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh971602">Name</a>


Read-only

Gets the name of the printer for this print queue.

 


## -members
The <b>IPrinterQueue</b> interface has these methods.
<table class="members" id="memberListMethods">
<tr>
<th align="left" width="37%">Method</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/jj991811">GetProperties</a>
</td>
<td align="left" width="63%">
Gets the properties in the property bag for the queue.

</td>
</tr>
<tr data="declared;">
<td align="left" width="37%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh846197">SendBidiQuery</a>
</td>
<td align="left" width="63%">
Performs an asynchronous refresh operation with the specified query, and invokes the <a href="https://msdn.microsoft.com/D0CD9950-DF73-4D46-B901-FA45BA88D3CF">IPrinterQueueEvent::OnBidiResponseReceived</a> method.

</td>
</tr>
</table>Gets the properties in the property bag for the queue.

Performs an asynchronous refresh operation with the specified query, and invokes the <a href="https://msdn.microsoft.com/D0CD9950-DF73-4D46-B901-FA45BA88D3CF">IPrinterQueueEvent::OnBidiResponseReceived</a> method.

 

The <b xmlns:loc="http://microsoft.com/wdcml/l10n">IPrinterQueue</b> interface has these properties.
<table class="members" id="memberListProperties">
<tr>
<th align="left" width="27%">Property</th>
<th align="left" width="10%">Access type</th>
<th align="left" width="63%">Description</th>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh973215">Handle</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the underlying native handle for this print queue.

</td>
</tr>
<tr data="declared;">
<td align="left" width="27%" xml:space="preserve">

<a href="https://msdn.microsoft.com/library/windows/hardware/hh971602">Name</a>


</td>
<td align="left" width="10%">
Read-only

</td>
<td align="left" width="63%">
Gets the name of the printer for this print queue.

</td>
</tr>
</table>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh973215">Handle</a>


Read-only

Gets the underlying native handle for this print queue.


<a href="https://msdn.microsoft.com/library/windows/hardware/hh971602">Name</a>


Read-only

Gets the name of the printer for this print queue.

 


## -remarks
Any event sink that implements <a href="..\printerextension\nn-printerextension-iprinterqueueevent.md">IPrinterQueueEvent</a> is connected to the associated event source, <b>IPrinterQueue</b>, via the <a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a> mechanism. You must retrieve a pointer to the <b>IConnectionPoint</b> interface by invoking <b>QueryInterface</b> on the <b>IPrinterQueue</b> object.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

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
<dt><a href="http://msdn.microsoft.com/en-us/library/windows/desktop/ms694318(v=vs.85).aspx">IConnectionPoint</a></dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprinterqueueevent.md">IPrinterQueueEvent</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue interface%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

