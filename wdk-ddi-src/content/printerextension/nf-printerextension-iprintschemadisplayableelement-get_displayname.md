---
UID: NF:printerextension.IPrintSchemaDisplayableElement.get_DisplayName
title: IPrintSchemaDisplayableElement::get_DisplayName method
author: windows-driver-content
description: Gets a displayable string for this item.
old-location: print\iprintschemadisplayableelement_displayname.htm
old-project: print
ms.assetid: 8DF71F10-1043-47E8-98E0-BB100B2AAF26
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: DisplayName property [Print Devices], DisplayName property [Print Devices], IPrintSchemaDisplayableElement interface, IPrintSchemaDisplayableElement, IPrintSchemaDisplayableElement interface [Print Devices], DisplayName property, IPrintSchemaDisplayableElement.DisplayName, IPrintSchemaDisplayableElement::get_DisplayName, get_DisplayName, get_DisplayName,IPrintSchemaDisplayableElement.get_DisplayName, print.iprintschemadisplayableelement_displayname, printerextension/IPrintSchemaDisplayableElement::DisplayName, printerextension/IPrintSchemaDisplayableElement::get_DisplayName
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Printerextension.h
api_name:
-	IPrintSchemaDisplayableElement.DisplayName
-	IPrintSchemaDisplayableElement.get_DisplayName
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_DisplayName method
Gets a displayable string for this item.

This property is read-only.

## Syntax

````
HRESULT get_DisplayName(
  [out, retval] BSTR *pbstrDisplayName
);
````

## Parameters

`pbstrDisplayName`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemadisplayableelement.md">IPrintSchemaDisplayableElement</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaDisplayableElement::DisplayName property%20 RELEASE:%20(2/23/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>