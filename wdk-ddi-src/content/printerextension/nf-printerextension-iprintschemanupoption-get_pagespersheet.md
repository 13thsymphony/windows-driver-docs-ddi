---
UID: NF:printerextension.IPrintSchemaNUpOption.get_PagesPerSheet
title: IPrintSchemaNUpOption::get_PagesPerSheet method
author: windows-driver-content
description: Gets the number of pages per sheet.
old-location: print\iprintschemanupoption_pagespersheet.htm
old-project: print
ms.assetid: 036F59B3-962D-446C-A736-CDA1D5199CF5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaNUpOption, IPrintSchemaNUpOption interface [Print Devices], PagesPerSheet property, IPrintSchemaNUpOption.PagesPerSheet, IPrintSchemaNUpOption::get_PagesPerSheet, PagesPerSheet property [Print Devices], PagesPerSheet property [Print Devices], IPrintSchemaNUpOption interface, get_PagesPerSheet, get_PagesPerSheet,IPrintSchemaNUpOption.get_PagesPerSheet, print.iprintschemanupoption_pagespersheet, printerextension/IPrintSchemaNUpOption::PagesPerSheet, printerextension/IPrintSchemaNUpOption::get_PagesPerSheet
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
-	IPrintSchemaNUpOption.PagesPerSheet
-	IPrintSchemaNUpOption.get_PagesPerSheet
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_PagesPerSheet method
Gets the number of pages per sheet.

This property is read-only.

## Syntax

````
HRESULT get_PagesPerSheet(
  [out, retval] ULONG *pulPagesPerSheet
);
````

## Parameters

`pulPagesPerSheet`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemanupoption.md">IPrintSchemaNUpOption</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaNUpOption::PagesPerSheet property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>