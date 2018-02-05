---
UID : NN:printerextension.IPrintSchemaTicket2
title : IPrintSchemaTicket2
author : windows-driver-content
description : The IPrintSchemaTicket2 interface is an extension to the IPrintSchemaTicket interface, which provides wrapper methods over a print ticket document.
old-location : print\iprintschematicket2.htm
old-project : print
ms.assetid : 52D9FA01-578B-43C2-A0B1-F3CD0BAAFAE4
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : print.iprintschematicket2, IPrintSchemaTicket2 interface [Print Devices], IPrintSchemaTicket2 interface [Print Devices], described, IPrintSchemaTicket2, printerextension/IPrintSchemaTicket2
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : interface
req.header : printerextension.h
req.include-header : 
req.target-type : Windows
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : printerextension.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PrintSchemaSelectionType
req.product : Windows 10 or later.
---

# IPrintSchemaTicket2 interface

The  <b>IPrintSchemaTicket2</b> interface is an extension to the <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> interface, which provides wrapper methods over a print ticket document.

## Methods

<p>The <b>IPrintSchemaTicket2</b> interface has these methods.</p>

| Method | Description |
| ---- |:---- |
| [printerextension.IPrintSchemaTicket2.GetParameterInitializer](nf-printerextension-iprintschematicket2-getparameterinitializer.md) | The GetParameterInitializer method retrieves the IPrintSchemaParameterInitializer object, and it represents the &lt;psf:ParameterInit&gt; element in the PrintTicket XML. |

## Remarks



## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket2 interface%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>