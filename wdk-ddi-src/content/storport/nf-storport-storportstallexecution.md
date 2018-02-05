---
UID : NF:storport.StorPortStallExecution
title : StorPortStallExecution function
author : windows-driver-content
description : The StorPortStallExecution routine stalls the miniport driver.
old-location : storage\storportstallexecution.htm
old-project : storage
ms.assetid : d635d93b-3e69-4ce5-9dc0-60186417d009
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storprt_8cddf62f-d26d-4dd8-85f5-5bf35f74c1de.xml, storport/StorPortStallExecution, storage.storportstallexecution, StorPortStallExecution, StorPortStallExecution routine [Storage Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : storport.h
req.include-header : Storport.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : SpNoWait
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Storport.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : STOR_SPINLOCK
req.product : Windows 10 or later.
---


# StorPortStallExecution function
The <b>StorPortStallExecution</b> routine stalls the miniport driver.

## Syntax

````
STORPORT_API VOID StorPortStallExecution(
  _In_ ULONG Delay
);
````

## Parameters

`Delay`

Specifies the delay interval, in microseconds. The given value must be less than a full millisecond.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |
| **DDI compliance rules** | SpNoWait |

## See Also

<a href="..\srb\nf-srb-scsiportstallexecution.md">ScsiPortStallExecution</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortStallExecution routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>