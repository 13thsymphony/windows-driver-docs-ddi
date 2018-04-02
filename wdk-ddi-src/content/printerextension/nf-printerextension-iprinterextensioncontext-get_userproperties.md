---
UID: NF:printerextension.IPrinterExtensionContext.get_UserProperties
title: IPrinterExtensionContext::get_UserProperties method
author: windows-driver-content
description: Gets the user property bag for this app.
old-location: print\iprinterextensioncontext_userproperties.htm
old-project: print
ms.assetid: 21B370C9-BDF7-42A6-B0CC-BC9B19F9D2D5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IPrinterExtensionContext, IPrinterExtensionContext interface [Print Devices], UserProperties property, IPrinterExtensionContext.UserProperties, IPrinterExtensionContext::get_UserProperties, UserProperties property [Print Devices], UserProperties property [Print Devices], IPrinterExtensionContext interface, get_UserProperties, get_UserProperties,IPrinterExtensionContext.get_UserProperties, print.iprinterextensioncontext_userproperties, printerextension/IPrinterExtensionContext::UserProperties, printerextension/IPrinterExtensionContext::get_UserProperties
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
-	IPrinterExtensionContext.UserProperties
-	IPrinterExtensionContext.get_UserProperties
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterExtensionContext::get_UserProperties method
Gets the user property bag for this app.

This property is read-only.

## Syntax

```
HRESULT get_UserProperties(
  IPrinterPropertyBag **ppPropertyBag
);
```

## Parameters

`ppPropertyBag`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406649">IPrinterExtensionContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439547">IPrinterPropertyBag</a>