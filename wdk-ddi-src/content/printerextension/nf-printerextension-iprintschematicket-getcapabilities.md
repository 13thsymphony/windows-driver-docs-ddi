---
UID: NF:printerextension.IPrintSchemaTicket.GetCapabilities
title: IPrintSchemaTicket::GetCapabilities method
author: windows-driver-content
description: Gets an IPrintSchemaCapabilities object that represents the printer capabilities based on the current settings of this IPrintSchemaTicket object.
old-location: print\iprintschematicket_getcapabilities.htm
old-project: print
ms.assetid: 5556BD5E-6489-4CCF-8C62-DDA53AD9F368
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: print.iprintschematicket_getcapabilities, IPrintSchemaTicket, IPrintSchemaTicket interface [Print Devices], GetCapabilities method, IPrintSchemaTicket::GetCapabilities, printerextension/IPrintSchemaTicket::GetCapabilities, GetCapabilities method [Print Devices], GetCapabilities, GetCapabilities method [Print Devices], IPrintSchemaTicket interface
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	printerextension.h
apiname:
-	IPrintSchemaTicket.GetCapabilities
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# GetCapabilities method
Gets an <a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a> object that represents the printer capabilities based on the current settings of this <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object.

## Syntax

````
HRESULT GetCapabilities(
  [out, retval] IPrintSchemaCapabilities **ppPrintCapabilities
);
````

## Parameters

`ppCapabilities`




## Return Value

This method returns an <b>HRESULT</b> value.

## Remarks

Because this method retrieves a new PrintCapabilities document every time it is invoked, it is recommended that you invoke this method only when the <a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a> object has been modified.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/DF788C8F-DA60-47F1-83DB-2E1947E41142">IPrintSchemaTicket::put_JobCopiesAllDocuments</a>

<a href="https://msdn.microsoft.com/5E7F2292-1F71-4581-8E34-86F1464EC08F">IPrintSchemaElement::XmlNode</a>

<a href="..\printerextension\nn-printerextension-iprintschemacapabilities.md">IPrintSchemaCapabilities</a>

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>

<a href="https://msdn.microsoft.com/C22BC037-05D2-4F44-8704-D1D56909B603">IPrintSchemaFeature::SelectedOption</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket::GetCapabilities method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>