---
UID: NF:printerextension.IPrintSchemaPageMediaSizeOption.get_HeightInMicrons
title: IPrintSchemaPageMediaSizeOption::get_HeightInMicrons method
author: windows-driver-content
description: Gets the height of the page in microns.
old-location: print\iprintschemapagemediasizeoption_heightinmicrons.htm
old-project: print
ms.assetid: B419BD5D-A3B7-46D1-8E6B-3100E0940842
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IPrintSchemaPageMediaSizeOption.HeightInMicrons, get_HeightInMicrons, print.iprintschemapagemediasizeoption_heightinmicrons, IPrintSchemaPageMediaSizeOption interface [Print Devices], HeightInMicrons property, IPrintSchemaPageMediaSizeOption::get_HeightInMicrons, HeightInMicrons property [Print Devices], IPrintSchemaPageMediaSizeOption interface, IPrintSchemaPageMediaSizeOption, printerextension/IPrintSchemaPageMediaSizeOption::HeightInMicrons, HeightInMicrons property [Print Devices], printerextension/IPrintSchemaPageMediaSizeOption::get_HeightInMicrons
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
-	IPrintSchemaPageMediaSizeOption.HeightInMicrons
-	IPrintSchemaPageMediaSizeOption.get_HeightInMicrons
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_HeightInMicrons method
Gets the height of the page in microns.

This property is read-only.

## Syntax

````
HRESULT get_HeightInMicrons(
  [out, retval] ULONG *pulHeight
);
````

## Parameters

`pulHeight`




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

<a href="..\printerextension\nn-printerextension-iprintschemapagemediasizeoption.md">IPrintSchemaPageMediaSizeOption</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaPageMediaSizeOption::HeightInMicrons property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>