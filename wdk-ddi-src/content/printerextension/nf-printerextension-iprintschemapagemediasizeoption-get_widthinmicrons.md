---
UID: NF:printerextension.IPrintSchemaPageMediaSizeOption.get_WidthInMicrons
title: IPrintSchemaPageMediaSizeOption::get_WidthInMicrons method
author: windows-driver-content
description: Gets the width of the page in microns.
old-location: print\iprintschemapagemediasizeoption_widthinmicrons.htm
old-project: print
ms.assetid: D44C8782-DA25-4189-AECA-B899A4AA9279
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrintSchemaPageMediaSizeOption, IPrintSchemaPageMediaSizeOption interface [Print Devices], WidthInMicrons property, IPrintSchemaPageMediaSizeOption.WidthInMicrons, IPrintSchemaPageMediaSizeOption::get_WidthInMicrons, WidthInMicrons property [Print Devices], WidthInMicrons property [Print Devices], IPrintSchemaPageMediaSizeOption interface, get_WidthInMicrons, get_WidthInMicrons,IPrintSchemaPageMediaSizeOption.get_WidthInMicrons, print.iprintschemapagemediasizeoption_widthinmicrons, printerextension/IPrintSchemaPageMediaSizeOption::WidthInMicrons, printerextension/IPrintSchemaPageMediaSizeOption::get_WidthInMicrons
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
-	IPrintSchemaPageMediaSizeOption.WidthInMicrons
-	IPrintSchemaPageMediaSizeOption.get_WidthInMicrons
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_WidthInMicrons method
Gets the width of the page in microns.

This property is read-only.

## Syntax

````
HRESULT get_WidthInMicrons(
  [out, retval] ULONG *pulWidth
);
````

## Parameters

`pulWidth`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemapagemediasizeoption.md">IPrintSchemaPageMediaSizeOption</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaPageMediaSizeOption::WidthInMicrons property%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>