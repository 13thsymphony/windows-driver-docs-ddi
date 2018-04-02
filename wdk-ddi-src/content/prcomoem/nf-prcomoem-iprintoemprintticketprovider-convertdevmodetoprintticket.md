---
UID: NF:prcomoem.IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket
title: IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket method
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket method converts a DEVMODEW structure into a print ticket.
old-location: print\iprintoemprintticketprovider_convertdevmodetoprintticket.htm
old-project: print
ms.assetid: b2e029b7-32c0-4cef-8388-9d30aa5610d3
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, ., :, C, ConvertDevModeToPrintTicket, ConvertDevModeToPrintTicket method [Print Devices], ConvertDevModeToPrintTicket method [Print Devices], IPrintOemPrintTicketProvider interface, ConvertDevModeToPrintTicket,IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket, D, I, IPrintOemPrintTicketProvider, IPrintOemPrintTicketProvider interface [Print Devices], ConvertDevModeToPrintTicket method, IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket, M, O, P, T, c, d, e, i, k, m, n, o, prcomoem/IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket, print.iprintoemprintticketprovider_convertdevmodetoprintticket, print_ticket-package_4605321f-640a-438b-a4cc-6e34ef5521b1.xml, r, t, v"
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
-	IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket
product:
- Windows
targetos: Windows
req.typenames: OEMPTOPTS, *POEMPTOPTS
req.product: Windows 10 or later.
---


# IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket method
The <code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> method converts a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure into a print ticket.

## Syntax

````
HRESULT ConvertDevModeToPrintTicket(
  [in]      ULONG            cbDevmode,
  [in]      PDEVMODE         pDevmode,
  [in]      ULONG            cbDrvPrivateSize,
  [in]      PVOID            pPrivateDevmode,
  [in, out] IXMLDOMDocument2 *pPrintTicket
);
````

## Parameters

`cbDevmode`

The size, in bytes, of the input <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure. The size includes both the public and private portions of this structure.

`pDevmode`

A pointer to the input DEVMODEW structure.

`cbDrvPrivateSize`

The size, in bytes, of the plug-in's private DEVMODEW structure.

`pPrivateDevmode`

A pointer to the plug-in's private <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure.

`pPrintTicket`

A pointer to the partially-completed print ticket. When <code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> returns, all of the entries in the print ticket should be filled in.


## Return Value

<code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> should return S_OK if the operation succeeds. Otherwise, this method should return a standard COM error code.

## Remarks

The core driver calls the <code>IPrintTicketProvider::ConvertDevModeToPrintTicket</code> method with an input print ticket that is populated with public and Unidrv-private or Pscript5-private features. The plug-in is free to set <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> settings in the public part or in the plug-in's private part, based on settings in the input print ticket. In addition to setting new DEVMODEW items, the plug-in can modify existing settings in the public portion of the DEVMODEW structure.

The DEVMODEW structure fields that correlate with the part of the DEVMODEW structure of interest to the client will already have been populated before <code>IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket</code> is called, including the public portion of the DEVMODEW structure and excluding the privately-defined values in the public portion of the DEVMODEW structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | prcomoem.h (include Prcomoem.h) |
| **Library** | prcomoem.h |

## See Also

<a href="..\prcomoem\nn-prcomoem-iprintoemprintticketprovider.md">IPrintOemPrintTicketProvider</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553167">IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode</a>