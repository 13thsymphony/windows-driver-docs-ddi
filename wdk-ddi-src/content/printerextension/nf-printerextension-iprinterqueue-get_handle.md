---
UID: NF:printerextension.IPrinterQueue.get_Handle
title: IPrinterQueue::get_Handle method
author: windows-driver-content
description: Gets the underlying native handle for this print queue.
old-location: print\iprinterqueue_handle.htm
old-project: print
ms.assetid: FE8A8822-28C8-4255-86A4-A77F17C1C281
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Handle property [Print Devices], Handle property [Print Devices], IPrinterQueue interface, IPrinterQueue, IPrinterQueue interface [Print Devices], Handle property, IPrinterQueue.Handle, IPrinterQueue::get_Handle, get_Handle, get_Handle,IPrinterQueue.get_Handle, print.iprinterqueue_handle, printerextension/IPrinterQueue::Handle, printerextension/IPrinterQueue::get_Handle
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
-	IPrinterQueue.Handle
-	IPrinterQueue.get_Handle
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# IPrinterQueue::get_Handle method
Gets the underlying native handle for this print queue.

This property is read-only.

## Syntax

```
HRESULT get_Handle(
  HANDLE *phPrinter
);
```

## Parameters

`phPrinter`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439635">IPrinterQueue</a>