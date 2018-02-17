---
UID: NF:printerextension.IPrintSchemaFeature.get_DisplayUI
title: IPrintSchemaFeature::get_DisplayUI method
author: windows-driver-content
description: Gets the setting that indicates whether or not to show the print UI.
old-location: print\iprintschemafeature_displayui.htm
old-project: print
ms.assetid: 47E8BF6E-7CBE-43B9-9F3F-D91E88FB02D4
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: DisplayUI property [Print Devices], IPrintSchemaFeature interface, IPrintSchemaFeature interface [Print Devices], DisplayUI property, IPrintSchemaFeature, IPrintSchemaFeature.DisplayUI, get_DisplayUI, print.iprintschemafeature_displayui, printerextension/IPrintSchemaFeature::DisplayUI, printerextension/IPrintSchemaFeature::get_DisplayUI, IPrintSchemaFeature::get_DisplayUI, DisplayUI property [Print Devices]
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
-	IPrintSchemaFeature.DisplayUI
-	IPrintSchemaFeature.get_DisplayUI
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_DisplayUI method
Gets the setting that indicates whether or not to show the print UI.

This property is read-only.

## Syntax

````
HRESULT get_DisplayUI(
  [out, retval] BOOL *pbShow
);
````

## Parameters

`pbShow`




## Return Value

None

## Remarks

Note that the <b>DisplayUI</b> property  corresponds to the psk:DisplayUI element. If the XML value is unspecified or set to <i>Show</i>, then the Print system sets  <b>DisplayUI</b> to <b>TRUE.</b>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemafeature.md">IPrintSchemaFeature</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaFeature::DisplayUI property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>