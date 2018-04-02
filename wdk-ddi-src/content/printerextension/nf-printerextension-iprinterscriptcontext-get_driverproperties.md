---
UID: NF:printerextension.IPrinterScriptContext.get_DriverProperties
title: IPrinterScriptContext::get_DriverProperties method
author: windows-driver-content
description: Provides access to the driver property bag, if the property bag is present.
old-location: print\iprinterscriptcontext_driverproperties.htm
old-project: print
ms.assetid: 73BE6E2A-0C46-4C3F-8888-5FE8386A1F50
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DriverProperties property [Print Devices], DriverProperties property [Print Devices], IPrinterScriptContext interface, IPrinterScriptContext, IPrinterScriptContext interface [Print Devices], DriverProperties property, IPrinterScriptContext.DriverProperties, IPrinterScriptContext::get_DriverProperties, get_DriverProperties, get_DriverProperties,IPrinterScriptContext.get_DriverProperties, print.iprinterscriptcontext_driverproperties, printerextension/IPrinterScriptContext::DriverProperties, printerextension/IPrinterScriptContext::get_DriverProperties
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
-	IPrinterScriptContext.DriverProperties
-	IPrinterScriptContext.get_DriverProperties
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterScriptContext::get_DriverProperties method
Provides access to the driver property bag, if the property bag is present.

This property is read-only.

## Syntax

```
HRESULT get_DriverProperties(
  IPrinterScriptablePropertyBag **ppPropertyBag
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

<a href="https://msdn.microsoft.com/library/windows/hardware/hh768279">IPrinterScriptContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh973217">IPrinterScriptablePropertyBag</a>