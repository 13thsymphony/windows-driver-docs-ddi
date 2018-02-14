---
UID: NF:printerextension.IPrintSchemaElement.get_NamespaceUri
title: IPrintSchemaElement::get_NamespaceUri method
author: windows-driver-content
description: Gets the namespace URI value of the &#0034;name&#0034; attribute of this node.
old-location: print\iprintschemaelement_namespaceuri.htm
old-project: print
ms.assetid: F03FFC6A-6186-4C59-97EB-0D954BF198D3
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: get_NamespaceUri, printerextension/IPrintSchemaElement::NamespaceUri, IPrintSchemaElement, NamespaceUri property [Print Devices], IPrintSchemaElement interface, IPrintSchemaElement interface [Print Devices], NamespaceUri property, printerextension/IPrintSchemaElement::get_NamespaceUri, NamespaceUri property [Print Devices], IPrintSchemaElement.NamespaceUri, IPrintSchemaElement::get_NamespaceUri, print.iprintschemaelement_namespaceuri
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
req.lib: printerextension.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Printerextension.h
apiname:
-	IPrintSchemaElement.NamespaceUri
-	IPrintSchemaElement.get_NamespaceUri
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_NamespaceUri method
Gets the namespace URI  value of the "name" attribute of this node.

This property is read-only.

## Syntax

````
HRESULT get_NamespaceUri(
  [out, retval] BSTR *pbstrNamespaceUri
);
````

## Parameters

`pbstrNamespaceUri`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemaelement.md">IPrintSchemaElement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaElement::NamespaceUri property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>