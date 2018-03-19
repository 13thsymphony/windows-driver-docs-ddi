---
UID: NF:printerextension.IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons
title: IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons method
author: windows-driver-content
description: Gets the horizontal distance between the origin and the bounding limit of the application media size.
old-location: print\iprintschemapageimageablesize_extentwidthinmicrons.htm
old-project: print
ms.assetid: B30CD277-ADE2-45F7-BE73-CF738843D9B9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ExtentWidthInMicrons property [Print Devices], ExtentWidthInMicrons property [Print Devices], IPrintSchemaPageImageableSize interface, IPrintSchemaPageImageableSize, IPrintSchemaPageImageableSize interface [Print Devices], ExtentWidthInMicrons property, IPrintSchemaPageImageableSize.ExtentWidthInMicrons, IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons, get_ExtentWidthInMicrons, get_ExtentWidthInMicrons,IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons, print.iprintschemapageimageablesize_extentwidthinmicrons, printerextension/IPrintSchemaPageImageableSize::ExtentWidthInMicrons, printerextension/IPrintSchemaPageImageableSize::get_ExtentWidthInMicrons
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
-	IPrintSchemaPageImageableSize.ExtentWidthInMicrons
-	IPrintSchemaPageImageableSize.get_ExtentWidthInMicrons
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_ExtentWidthInMicrons method
Gets the horizontal distance between the origin and the bounding limit of the application media size.

This property is read-only.

## Syntax

````
HRESULT get_ExtentWidthInMicrons(
  [out, retval] ULONG *pulExtentWidth
);
````

## Parameters

`pulExtentWidth`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemapageimageablesize.md">IPrintSchemaPageImageableSize</a>