---
UID: NF:prdrvcom.ConvertDevModeToPrintTicket
title: ConvertDevModeToPrintTicket function
author: windows-driver-content
description: The IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket method converts a DEVMODEW structure into a print ticket.
old-location: print\iprintoemprintticketprovider_convertdevmodetoprintticket.htm
old-project: print
ms.assetid: b2e029b7-32c0-4cef-8388-9d30aa5610d3
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ConvertDevModeToPrintTicket, ConvertDevModeToPrintTicket method [Print Devices], ConvertDevModeToPrintTicket method [Print Devices], IPrintOemPrintTicketProvider interface, IPrintOemPrintTicketProvider interface [Print Devices], ConvertDevModeToPrintTicket method, IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket, prdrvcom/IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket, print.iprintoemprintticketprovider_convertdevmodetoprintticket, print_ticket-package_4605321f-640a-438b-a4cc-6e34ef5521b1.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: prdrvcom.h
req.include-header: Prdrvcom.h
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	prdrvcom.h
api_name:
-	IPrintOemPrintTicketProvider.ConvertDevModeToPrintTicket
product: Windows
targetos: Windows
req.typenames: SHIMOPTS, *PSHIMOPTS
req.product: Windows 10 or later.
---


# ConvertDevModeToPrintTicket function
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
| **Header** | prdrvcom.h (include Prdrvcom.h) |
| **Library** | NtosKrnl.exe |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553167">IPrintOemPrintTicketProvider::ConvertPrintTicketToDevMode</a>



<a href="..\prcomoem\nn-prcomoem-iprintoemprintticketprovider.md">IPrintOemPrintTicketProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintOemPrintTicketProvider::ConvertDevModeToPrintTicket method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>