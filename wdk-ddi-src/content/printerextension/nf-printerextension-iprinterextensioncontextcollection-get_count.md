---
UID: NF:printerextension.IPrinterExtensionContextCollection.get_Count
title: IPrinterExtensionContextCollection::get_Count method
author: windows-driver-content
description: Gets a count of the number of IPrinterExtensionContext objects in the collection.
old-location: print\iprinterextensioncontextcollection_count.htm
old-project: print
ms.assetid: F2279727-168D-451B-8EDB-8A4A36ACA08F
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Count property [Print Devices], Count property [Print Devices], IPrinterExtensionContextCollection interface, IPrinterExtensionContextCollection, IPrinterExtensionContextCollection interface [Print Devices], Count property, IPrinterExtensionContextCollection.Count, IPrinterExtensionContextCollection::get_Count, get_Count, get_Count,IPrinterExtensionContextCollection.get_Count, print.iprinterextensioncontextcollection_count, printerextension/IPrinterExtensionContextCollection::Count, printerextension/IPrinterExtensionContextCollection::get_Count
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
-	IPrinterExtensionContextCollection.Count
-	IPrinterExtensionContextCollection.get_Count
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterExtensionContextCollection::get_Count method
Gets a count of the number of <a href="https://msdn.microsoft.com/library/windows/hardware/hh406649">IPrinterExtensionContext</a> objects in the collection.

This property is read-only.

## Syntax

```
HRESULT get_Count(
  ULONG *pulCount
);
```

## Parameters

`pulCount`




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



<a href="https://msdn.microsoft.com/library/windows/hardware/hh846191">IPrinterExtensionContextCollection</a>