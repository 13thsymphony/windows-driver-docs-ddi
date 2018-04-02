---
UID: NF:printerextension.IPrinterExtensionEventArgs.get_SourceApplication
title: IPrinterExtensionEventArgs::get_SourceApplication method
author: windows-driver-content
description: Gets the name of the application that invoked the printer extension.
old-location: print\iprinterextensioneventargs_sourceapplication.htm
old-project: print
ms.assetid: 98A8427B-24F7-43D2-A0AD-76E3BC085BCA
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionEventArgs, IPrinterExtensionEventArgs interface [Print Devices], SourceApplication property, IPrinterExtensionEventArgs.SourceApplication, IPrinterExtensionEventArgs::get_SourceApplication, SourceApplication property [Print Devices], SourceApplication property [Print Devices], IPrinterExtensionEventArgs interface, get_SourceApplication, get_SourceApplication,IPrinterExtensionEventArgs.get_SourceApplication, print.iprinterextensioneventargs_sourceapplication, printerextension/IPrinterExtensionEventArgs::SourceApplication, printerextension/IPrinterExtensionEventArgs::get_SourceApplication
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
-	IPrinterExtensionEventArgs.SourceApplication
-	IPrinterExtensionEventArgs.get_SourceApplication
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterExtensionEventArgs::get_SourceApplication method
Gets the name of the application that invoked the printer extension.

This property is read-only.

## Syntax

```
HRESULT get_SourceApplication(
  BSTR *pbstrApplication
);
```

## Parameters

`pbstrApplication`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh973207">IPrinterExtensionEventArgs</a>