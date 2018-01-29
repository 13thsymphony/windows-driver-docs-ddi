---
UID : NF:printerextension.IPrintSchemaAsyncOperation.Cancel
title : IPrintSchemaAsyncOperation::Cancel method
author : windows-driver-content
description : Cancels the asynchronous PrintSchema operation.
old-location : print\iprintschemaasyncoperation_cancel.htm
old-project : print
ms.assetid : 08DC764B-4410-4D7C-B199-29E38BA09CA6
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : printerextension/IPrintSchemaAsyncOperation::Cancel, print.iprintschemaasyncoperation_cancel, IPrintSchemaAsyncOperation interface [Print Devices], Cancel method, IPrintSchemaAsyncOperation::Cancel, Cancel method [Print Devices], IPrintSchemaAsyncOperation interface, Cancel, IPrintSchemaAsyncOperation, Cancel method [Print Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : printerextension.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : printerextension.h
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : PrintSchemaSelectionType
req.product : Windows 10 or later.
---


# Cancel method
Cancels the asynchronous PrintSchema operation.

## Syntax

````
HRESULT Cancel(
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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | printerextension.h |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschemaasyncoperation.md">IPrintSchemaAsyncOperation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaAsyncOperation::Cancel method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>