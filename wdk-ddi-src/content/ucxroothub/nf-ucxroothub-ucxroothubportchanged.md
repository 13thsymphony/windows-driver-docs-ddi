---
UID: NF:ucxroothub.UcxRootHubPortChanged
title: UcxRootHubPortChanged function
author: windows-driver-content
description: Notifies UCX about a new port change event on the host controller.
old-location: buses\_ucxroothubportchanged.htm
old-project: usbref
ms.assetid: 7984308D-4C8E-4481-8770-2430552B00E8
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: UcxRootHubPortChanged, UcxRootHubPortChanged method [Buses], buses._ucxroothubportchanged, ucxroothub/UcxRootHubPortChanged
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	ucxroothub.h
api_name:
-	UcxRootHubPortChanged
product: Windows
targetos: Windows
req.typenames: TRISTATE
req.product: Windows 10 or later.
---


# UcxRootHubPortChanged function
Notifies UCX about a new port change event on the host controller.

## Syntax

````
void UcxRootHubPortChanged(
  [in] UCXROOTHUB UcxRootHub
);
````

## Parameters

`UcxRootHub`

A handle to the root hub object. The client driver retrieved the handle in a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>.


## Return Value

This method does not return a value.

## Remarks

This method causes interrupt transfers to be sent to the host controller. UCX invokes the client driver's implementation of the <a href="..\ucxroothub\nc-ucxroothub-evt_ucx_roothub_interrupt_tx.md">EVT_UCX_ROOTHUB_INTERRUPT_TX</a> event callback.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10  |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxroothub.h (include Ucxclass.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt188048">UcxRootHubCreate</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UcxRootHubPortChanged method%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>