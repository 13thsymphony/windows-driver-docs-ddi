---
UID: NF:printerextension.IPrinterQueue.get_Handle
title: IPrinterQueue::get_Handle method
author: windows-driver-content
description: Gets the underlying native handle for this print queue.
old-location: print\iprinterqueue_handle.htm
old-project: print
ms.assetid: FE8A8822-28C8-4255-86A4-A77F17C1C281
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: Handle property [Print Devices], get_Handle, print.iprinterqueue_handle, Handle property [Print Devices], IPrinterQueue interface, IPrinterQueue, printerextension/IPrinterQueue::get_Handle, IPrinterQueue.Handle, printerextension/IPrinterQueue::Handle, IPrinterQueue interface [Print Devices], Handle property, IPrinterQueue::get_Handle
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
-	IPrinterQueue.Handle
-	IPrinterQueue.get_Handle
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# get_Handle method
Gets the underlying native handle for this print queue.

This property is read-only.

## Syntax

````
HRESULT get_Handle(
  [out, retval] HANDLE *phPrinter
);
````

## Parameters

`phPrinter`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Windows |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprinterqueue.md">IPrinterQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterQueue::Handle property%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>