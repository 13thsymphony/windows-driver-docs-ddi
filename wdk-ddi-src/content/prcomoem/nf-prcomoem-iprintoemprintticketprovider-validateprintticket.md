---
UID: NF.prcomoem.IPrintOemPrintTicketProvider.ValidatePrintTicket
title: IPrintOemPrintTicketProvider::ValidatePrintTicket
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::ValidatePrintTicket method validates a print ticket.
old-location: print\iprintoemprintticketprovider_validateprintticket.htm
ms.assetid: 359f1a4b-8bcc-4c4a-97d7-6515993765e3
ms.author: windowsdriverdev
ms.date: 10/24/2017
ms.topic: function
ms.prod: windows-hardware
ms.technology: print
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPrintOemPrintTicketProvider.ValidatePrintTicket
req.alt-loc: prcomoem.h
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
ms.keywords: IPrintOemPrintTicketProvider, ValidatePrintTicket, IPrintOemPrintTicketProvider::ValidatePrintTicket
req.iface: IPrintOemPrintTicketProvider
req.product: Windows 10 or later.
---

# IPrintOemPrintTicketProvider::ValidatePrintTicket method



## -description
<p>The <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> method validates a print ticket.</p>


## -syntax

````
HRESULT ValidatePrintTicket(
  [in, out] IXMLDOMDocument2 *pPrintTicket
);
````


## -parameters
<dl>

### -param <i>pPrintTicket</i> [in, out]

<dd>
<p>A pointer to an input print ticket. When <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> successfully returns, <i>pPrintTicket</i> points to a validated print ticket.</p>
</dd>
</dl>

## -returns
<p><code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> should return S_NO_CONFLICT or S_CONFLICT_RESOLVED if the operation succeeds. Otherwise, this method should return a standard COM error code. Note that Unidrv and Pscript do not consider S_OK to mean successful completion for this method.</p>

## -remarks
<p>If necessary, the <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code>  method should perform any conflict resolution, by inspecting the settings made in the public and Unidrv-private parts of the print ticket, to ensure that the resulting print ticket is valid, and that all of the constraints are resolved. If any required nodes are not present in the original print ticket, <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> can add them to the returned print ticket.</p>

<p>If necessary, the <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code>  method should perform any conflict resolution, by inspecting the settings made in the public and Unidrv-private parts of the print ticket, to ensure that the resulting print ticket is valid, and that all of the constraints are resolved. If any required nodes are not present in the original print ticket, <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> can add them to the returned print ticket.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Prcomoem.h (include Prcomoem.h)</dt>
</dl>
</td>
</tr>
</table>