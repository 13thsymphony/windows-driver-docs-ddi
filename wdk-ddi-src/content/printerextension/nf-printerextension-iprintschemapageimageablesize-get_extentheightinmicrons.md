---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_ExtentHeightInMicrons
title: IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons method
author: windows-driver-content
description: Gets the vertical distance between the origin and the bounding limit of the canvas application media size.
old-location: print\iprintschemapageimageablesize_extentheightinmicrons.htm
old-project: print
ms.assetid: AA305230-B194-465F-936E-24FDE9929EAC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ExtentHeightInMicrons property [Print Devices], ExtentHeightInMicrons property [Print Devices], IPrintSchemaPageImageableSize interface, IPrintSchemaPageImageableSize, IPrintSchemaPageImageableSize interface [Print Devices], ExtentHeightInMicrons property, IPrintSchemaPageImageableSize.ExtentHeightInMicrons, IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons, get_ExtentHeightInMicrons, get_ExtentHeightInMicrons,IPrintSchemaPageImageableSize.get_ExtentHeightInMicrons, print.iprintschemapageimageablesize_extentheightinmicrons, printerextension/IPrintSchemaPageImageableSize::ExtentHeightInMicrons, printerextension/IPrintSchemaPageImageableSize::get_ExtentHeightInMicrons
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
-	IPrintSchemaPageImageableSize.ExtentHeightInMicrons
-	IPrintSchemaPageImageableSize.get_ExtentHeightInMicrons
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_ExtentHeightInMicrons method
Gets the vertical distance between the origin and the bounding limit of the canvas application media size.

This property is read-only.

## Syntax

````
HRESULT get_ExtentHeightInMicrons(
  [out, retval] ULONG *pulExtentHeight
);
````

## Parameters

`pulExtentHeight`




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

<a href="..\printerextension\nn-printerextension-iprintschemapageimageablesize.md">IPrintSchemaPageImageableSize</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaPageImageableSize::ExtentHeightInMicrons property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>