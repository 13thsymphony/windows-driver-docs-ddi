---
UID: NF:printerextension.IPrintSchemaTicket.NotifyXmlChanged
title: IPrintSchemaTicket::NotifyXmlChanged method
author: windows-driver-content
description: Notifies the print system that the XML DOM object has changed.
old-location: print\iprintschematicket_notifyxmlchanged.htm
old-project: print
ms.assetid: B9A0C9EC-6C37-4C42-A10A-8CEE028C5998
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices], NotifyXmlChanged method, IPrintSchemaTicket::NotifyXmlChanged, NotifyXmlChanged method [Print Devices], NotifyXmlChanged method [Print Devices], IPrintSchemaTicket interface, NotifyXmlChanged,IPrintSchemaTicket.NotifyXmlChanged, print.iprintschematicket_notifyxmlchanged, printerextension/IPrintSchemaTicket::NotifyXmlChanged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
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
-	IPrintSchemaTicket.NotifyXmlChanged
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaTicket::NotifyXmlChanged method
Notifies the print system that the XML DOM object has changed.

## Syntax

```
HRESULT NotifyXmlChanged(

);
```

## Parameters

This function has no parameters.

## Return Value

This method returns an HRESULT value.

## Remarks

If the client retrieves the XML DOM object of the PrintTicket by calling <a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>, and makes direct modifications to the PrintTicket using XMLDOM APIs, then it is the responsibility of the client to call <b>IPrintSchemaTicket::NotifyXmlChanged</b> to notify the system that the PrintTicket content has been modified.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8  |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451398">IPrintSchemaTicket</a>