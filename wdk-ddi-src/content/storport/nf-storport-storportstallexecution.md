---
UID: NF:storport.StorPortStallExecution
title: StorPortStallExecution function
author: windows-driver-content
description: The StorPortStallExecution routine stalls the miniport driver.
old-location: storage\storportstallexecution.htm
old-project: storage
ms.assetid: d635d93b-3e69-4ce5-9dc0-60186417d009
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortStallExecution, StorPortStallExecution routine [Storage Devices], storage.storportstallexecution, storport/StorPortStallExecution, storprt_8cddf62f-d26d-4dd8-85f5-5bf35f74c1de.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: storport.h
req.include-header: Storport.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: SpNoWait
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Storport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Storport.lib
-	Storport.dll
api_name:
-	StorPortStallExecution
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
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