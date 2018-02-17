---
UID: NF:printerextension.IPrintSchemaTicket.CommitAsync
title: IPrintSchemaTicket::CommitAsync method
author: windows-driver-content
description: Gets an asynchronous PrintTicket commit operation context.
old-location: print\iprintschematicket_commitasync.htm
old-project: print
ms.assetid: CFEDCABF-A875-4A69-954D-267765350E9D
ms.author: windowsdriverdev
ms.date: 2/2/2018
ms.keywords: CommitAsync, CommitAsync method [Print Devices], printerextension/IPrintSchemaTicket::CommitAsync, print.iprintschematicket_commitasync, CommitAsync method [Print Devices], IPrintSchemaTicket interface, IPrintSchemaTicket::CommitAsync, IPrintSchemaTicket interface [Print Devices], CommitAsync method, IPrintSchemaTicket
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: printerextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
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
-	printerextension.h
apiname:
-	IPrintSchemaTicket.CommitAsync
product: Windows
targetos: Windows
req.typenames: PrintSchemaSelectionType
req.product: Windows 10 or later.
---


# CommitAsync method
Gets an  asynchronous PrintTicket commit operation context.

## Syntax

````
HRESULT CommitAsync(
  [in]  IPrintSchemaTicket         *pPrintTicketCommit,
  [out] IPrintSchemaAsyncOperation **ppAsyncOperation
);
````

## Parameters

`pPrintTicketCommit`

The print ticket to commit.

`ppAsyncOperation`

The asynchronous commit operation context.


## Return Value

This method returns an <b>HRESULT</b> value.

## Remarks

To perform the commit operation, call the <a href="https://msdn.microsoft.com/8AEA34AA-1A5E-43F6-8EE1-B1A078B6AEA3">IPrintSchemaAsyncOperation::Start</a> method to validate the given <i>pPrintTicketCommit</i> and then apply the validated PrintTicket settings to the current PrintTicket object. When the commit operation is completed or if an error occurs during the commit operation, the <a href="https://msdn.microsoft.com/B1599F21-D6DD-497D-9CD8-6C637ABAA33A">IPrintSchemaAsyncOperationEvent::Completed</a> event is fired.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | printerextension.h |
| **Library** | printerextension.h |

## See Also

<a href="..\printerextension\nn-printerextension-iprintschematicket.md">IPrintSchemaTicket</a>



<a href="https://msdn.microsoft.com/B1599F21-D6DD-497D-9CD8-6C637ABAA33A">IPrintSchemaAsyncOperationEvent::Completed</a>



<a href="https://msdn.microsoft.com/8AEA34AA-1A5E-43F6-8EE1-B1A078B6AEA3">IPrintSchemaAsyncOperation::Start</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20IPrintSchemaTicket::CommitAsync method%20 RELEASE:%20(2/2/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>