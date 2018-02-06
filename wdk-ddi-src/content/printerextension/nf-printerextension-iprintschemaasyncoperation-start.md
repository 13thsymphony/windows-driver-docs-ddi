---
UID: NF:printerextension.IPrintSchemaAsyncOperation.Start
title: IPrintSchemaAsyncOperation::Start method
author: windows-driver-content
description: Starts the asynchronous PrintSchema operation.
old-location: print\iprintschemaasyncoperation_start.htm
old-project: print
ms.assetid: 8AEA34AA-1A5E-43F6-8EE1-B1A078B6AEA3
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: IPrintSchemaAsyncOperation::Start, IPrintSchemaAsyncOperation interface [Print Devices], Start method, Start method [Print Devices], IPrintSchemaAsyncOperation interface, IPrintSchemaAsyncOperation, Start method [Print Devices], Start, printerextension/IPrintSchemaAsyncOperation::Start, print.iprintschemaasyncoperation_start
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
-	IPrintSchemaAsyncOperation.Start
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# Start method
Starts the asynchronous PrintSchema operation.

## Syntax

````
HRESULT Start(
    Void
);
````

## Parameters

This function has no parameters.

## Return Value

This method returns an <b>HRESULT</b> value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemaasyncoperation.md">IPrintSchemaAsyncOperation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaAsyncOperation::Start method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>