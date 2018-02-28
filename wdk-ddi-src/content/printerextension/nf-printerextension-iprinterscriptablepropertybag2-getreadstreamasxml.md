---
UID: NF:printerextension.IPrinterScriptablePropertyBag2.GetReadStreamAsXML
title: IPrinterScriptablePropertyBag2::GetReadStreamAsXML method
author: windows-driver-content
description: "."
old-location: print\iprinterscriptablepropertybag2_getreadstreamasxml.htm
old-project: print
ms.assetid: 1C6477C4-3038-4F8A-871F-7F336E631C8F
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: GetReadStreamAsXML method [Print Devices], GetReadStreamAsXML method [Print Devices], IPrinterScriptablePropertyBag2 interface, GetReadStreamAsXML,IPrinterScriptablePropertyBag2.GetReadStreamAsXML, IPrinterScriptablePropertyBag2, IPrinterScriptablePropertyBag2 interface [Print Devices], GetReadStreamAsXML method, IPrinterScriptablePropertyBag2::GetReadStreamAsXML, print.iprinterscriptablepropertybag2_getreadstreamasxml, printerextension/IPrinterScriptablePropertyBag2::GetReadStreamAsXML
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrinterScriptablePropertyBag2.GetReadStreamAsXML
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# GetReadStreamAsXML method


## Syntax

````
HRESULT GetReadStreamAsXML(
  [in]  BSTR     bstrName,
  [out] IUnknown **ppXmlNode
);
````

## Parameters

`bstrName`



`ppXmlNode`




## Return Value

If this method succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterscriptablepropertybag2.md">IPrinterScriptablePropertyBag2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterScriptablePropertyBag2::GetReadStreamAsXML method%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>