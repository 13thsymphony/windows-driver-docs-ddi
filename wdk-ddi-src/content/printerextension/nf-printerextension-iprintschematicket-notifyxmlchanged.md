---
UID : NF:printerextension.IPrintSchemaTicket.NotifyXmlChanged
title : IPrintSchemaTicket::NotifyXmlChanged method
author : windows-driver-content
description : Notifies the print system that the XML DOM object has changed.
old-location : print\iprintschematicket_notifyxmlchanged.htm
old-project : print
ms.assetid : B9A0C9EC-6C37-4C42-A10A-8CEE028C5998
ms.author : windowsdriverdev
ms.date : 1/8/2018
ms.keywords : IPrintSchemaTicket, IPrintSchemaTicket::NotifyXmlChanged, NotifyXmlChanged
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : printerextension.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : IPrintSchemaTicket.NotifyXmlChanged
req.alt-loc : Printerextension.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : PrintSchemaSelectionType
req.product : Windows 10 or later.
---


# NotifyXmlChanged method
Notifies the print system that the XML DOM object has changed.

## Syntax

````
HRESULT NotifyXmlChanged(
    None
);
````

## Parameters

This function has no parameters.

## Return Value

This method returns an HRESULT value.

## Remarks

If the client retrieves the XML DOM object of the PrintTicket by calling <a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>, and makes direct modifications to the PrintTicket using XMLDOM APIs, then it is the responsibility of the client to call <b>IPrintSchemaTicket::NotifyXmlChanged</b> to notify the system that the PrintTicket content has been modified.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | printerextension.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket::NotifyXmlChanged method%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>