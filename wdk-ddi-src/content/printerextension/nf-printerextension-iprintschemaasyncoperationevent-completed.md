---
UID: NF.printerextension.IPrintSchemaAsyncOperationEvent.Completed
title: IPrintSchemaAsyncOperationEvent::Completed
author: windows-driver-content
description: Is called when asynchronous PrintSchema operation that is represented by an IPrintSchemaAsyncOperation context is completed.
old-location: print\iprintschemaasyncoperationevent_completed.htm
old-project: print
ms.assetid: B1599F21-D6DD-497D-9CD8-6C637ABAA33A
ms.author: windowsdriverdev
ms.date: 11/24/2017
ms.keywords: IPrintSchemaAsyncOperationEvent, Completed, IPrintSchemaAsyncOperationEvent::Completed
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintSchemaAsyncOperationEvent.Completed
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
req.iface: IPrintSchemaAsyncOperationEvent
req.product: Windows 10 or later.
---

# IPrintSchemaAsyncOperationEvent::Completed method



## -description
<p>Is called when asynchronous PrintSchema operation that is represented by an <a href="..\printerextension\nn-printerextension-iprintschemaasyncoperation.md">IPrintSchemaAsyncOperation</a> context is completed.</p>


## -syntax

````
HRESULT Completed(
  [in] IPrintSchemaTicket *pTicket,
  [in] HRESULT            hrOperation
);
````


## -parameters
<dl>

### -param <i>pTicket</i> [in]

<dd>
<p>The print ticket.</p>
</dd>

### -param <i>hrOperation</i> [in]

<dd>
<p>The result of the completed operation.</p>
</dd>
</dl>

## -returns
<p>This method returns an <b>HRESULT</b> value.</p>

## -remarks
<p>The print ticket passed to the <b>Completed</b> method is the final validated, merged, or committed print ticket.</p>

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
<p>Version</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\printerextension\nn-printerextension-iprintschemaasyncoperationevent.md">IPrintSchemaAsyncOperationEvent</a>
</dt>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaAsyncOperationEvent::Completed method%20 RELEASE:%20(11/24/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
