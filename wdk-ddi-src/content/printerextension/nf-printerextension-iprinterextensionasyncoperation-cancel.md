---
UID : NF:printerextension.IPrinterExtensionAsyncOperation.Cancel
title : IPrinterExtensionAsyncOperation::Cancel method
author : windows-driver-content
description : Cancels the asynchronous operation.
old-location : print\iprinterextensionasyncoperation_cancel.htm
old-project : print
ms.assetid : B5E1F3C4-A131-411B-BBAB-6E8B69433E13
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : printerextension/IPrinterExtensionAsyncOperation::Cancel, IPrinterExtensionAsyncOperation, print.iprinterextensionasyncoperation_cancel, Cancel method [Print Devices], IPrinterExtensionAsyncOperation interface, IPrinterExtensionAsyncOperation interface [Print Devices], Cancel method, IPrinterExtensionAsyncOperation::Cancel, Cancel, Cancel method [Print Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : printerextension.h
req.include-header : 
req.target-type : Desktop
req.target-min-winverclnt : Windows 8.1
req.target-min-winversvr : Windows Server 2012 R2
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
Cancels the asynchronous operation.

## Syntax

````
HRESULT Cancel(
    void
);
````

## Parameters

This function has no parameters.

## Return Value

This method returns an <b>HRESULT</b> value.

## Remarks

This method guarantees that the callback object will not be invoked. No other form of status is provided, such as a way to check to see if the operation has been canceled.
Also, note that this method does not wait for the cancellation to be processed - it returns immediately.

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

<a href="..\printerextension\nn-printerextension-iprinterextensionasyncoperation.md">IPrinterExtensionAsyncOperation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrinterExtensionAsyncOperation::Cancel method%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>