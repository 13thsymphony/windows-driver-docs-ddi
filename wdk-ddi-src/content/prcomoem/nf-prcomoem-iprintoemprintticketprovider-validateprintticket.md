---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.ValidatePrintTicket
title: IPrintOemPrintTicketProvider::ValidatePrintTicket method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::ValidatePrintTicket method validates a print ticket.
old-location: print\iprintoemprintticketprovider_validateprintticket.htm
old-project: print
ms.assetid: 359f1a4b-8bcc-4c4a-97d7-6515993765e3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, I, IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider interface [Print Devices], ValidatePrintTicket method, IPrintOemPrintTicketProvider::ValidatePrintTicket, O, P, T, V, ValidatePrintTicket, ValidatePrintTicket method [Print Devices], ValidatePrintTicket method [Print Devices], IPrintOemPrintTicketProvider interface, ValidatePrintTicket,IPrintOemPrintTicketProvider.ValidatePrintTicket, a, c, d, e, i, k, l, m, n, o, prcomoem/IPrintOemPrintTicketProvider::ValidatePrintTicket, print.iprintoemprintticketprovider_validateprintticket, print_ticket-package_e7baf633-847b-4e0d-bffb-c723a05b672f.xml, r, t, v"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: prcomoem.h
req.include-header: Prcomoem.h
req.target-type: Desktop
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
req.lib: prcomoem.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	prcomoem.h
apiname:
-	IPrintOemPrintTicketProvider.ValidatePrintTicket
product: Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# ValidatePrintTicket method
The <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> method validates a print ticket.

## Syntax

````
HRESULT ValidatePrintTicket(
  [in, out] IXMLDOMDocument2 *pPrintTicket
);
````

## Parameters

`pPrintTicket`

A pointer to an input print ticket. When <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> successfully returns, <i>pPrintTicket</i> points to a validated print ticket.


## Return Value

<code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> should return S_NO_CONFLICT or S_CONFLICT_RESOLVED if the operation succeeds. Otherwise, this method should return a standard COM error code. Note that Unidrv and Pscript do not consider S_OK to mean successful completion for this method.

## Remarks

If necessary, the <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code>  method should perform any conflict resolution, by inspecting the settings made in the public and Unidrv-private parts of the print ticket, to ensure that the resulting print ticket is valid, and that all of the constraints are resolved. If any required nodes are not present in the original print ticket, <code>IPrintOemPrintTicketProvider::ValidatePrintTicket</code> can add them to the returned print ticket.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |
| **Library** | prcomoem.h |

## See Also

<a href="..\prcomoem\nn-prcomoem-iprintoemprintticketprovider.md">IPrintOemPrintTicketProvider</a>