---
UID: NF:printerextension.IPrintSchemaAsyncOperation.Cancel
title: IPrintSchemaAsyncOperation::Cancel method
author: windows-driver-content
description: Cancels the asynchronous PrintSchema operation.
old-location: print\iprintschemaasyncoperation_cancel.htm
old-project: print
ms.assetid: 08DC764B-4410-4D7C-B199-29E38BA09CA6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Cancel method [Print Devices], Cancel method [Print Devices], IPrintSchemaAsyncOperation interface, Cancel,IPrintSchemaAsyncOperation.Cancel, IPrintSchemaAsyncOperation, IPrintSchemaAsyncOperation interface [Print Devices], Cancel method, IPrintSchemaAsyncOperation::Cancel, print.iprintschemaasyncoperation_cancel, printerextension/IPrintSchemaAsyncOperation::Cancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
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
-	IPrintSchemaAsyncOperation.Cancel
product:
- Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrintSchemaAsyncOperation::Cancel method
Cancels the asynchronous PrintSchema operation.

## Syntax

```
HRESULT Cancel(

);
```

## Parameters

This function has no parameters.

## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451224">IPrintSchemaAsyncOperation</a>