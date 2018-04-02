---
UID: NF:printerextension.IPrinterExtensionContext.get_PrintSchemaTicket
title: IPrinterExtensionContext::get_PrintSchemaTicket method
author: windows-driver-content
description: Gets the print ticket that is appropriate for the queue and the activation.
old-location: print\iprinterextensioncontext_printschematicket.htm
old-project: print
ms.assetid: B217DE53-23B9-46BA-8B35-DA869EB9DBDA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionContext, IPrinterExtensionContext interface [Print Devices], PrintSchemaTicket property, IPrinterExtensionContext.PrintSchemaTicket, IPrinterExtensionContext::get_PrintSchemaTicket, PrintSchemaTicket property [Print Devices], PrintSchemaTicket property [Print Devices], IPrinterExtensionContext interface, get_PrintSchemaTicket, get_PrintSchemaTicket,IPrinterExtensionContext.get_PrintSchemaTicket, print.iprinterextensioncontext_printschematicket, printerextension/IPrinterExtensionContext::PrintSchemaTicket, printerextension/IPrinterExtensionContext::get_PrintSchemaTicket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterExtensionContext.PrintSchemaTicket
-	IPrinterExtensionContext.get_PrintSchemaTicket
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterExtensionContext::get_PrintSchemaTicket method
Gets the print ticket that is appropriate for the queue and the activation.

This property is read-only.

## Syntax

```
HRESULT get_PrintSchemaTicket(
  IPrintSchemaTicket **ppTicket
);
```

## Parameters

`ppTicket`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406649">IPrinterExtensionContext</a>