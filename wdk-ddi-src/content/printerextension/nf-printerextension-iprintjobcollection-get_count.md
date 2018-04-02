---
UID: NF:printerextension.IPrintJobCollection.get_Count
title: IPrintJobCollection::get_Count method
author: windows-driver-content
description: Gets the number of jobs in the print queue.
old-location: print\iprintjobcollection_count.htm
old-project: print
ms.assetid: B44C8023-CB5F-4381-8A75-CA086E989BAC
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Count property [Print Devices], Count property [Print Devices], IPrintJobCollection interface, IPrintJobCollection, IPrintJobCollection interface [Print Devices], Count property, IPrintJobCollection.Count, IPrintJobCollection::get_Count, get_Count,IPrintJobCollection.get_Count, print.iprintjobcollection_count, printerextension/IPrintJobCollection::Count, printerextension/IPrintJobCollection::get_Count
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
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
-	IPrintJobCollection.Count
-	IPrintJobCollection.get_Count
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintJobCollection::get_Count method
Gets the number of jobs in the print queue.

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
| **Windows version** | Windows 8.1 Windows Server 2012 R2 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265397">IPrintJobCollection</a>