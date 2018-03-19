---
UID: NF:storport.StorPortMoveMemory
title: StorPortMoveMemory function
author: windows-driver-content
description: The StorPortMoveMemory routine copies memory from one buffer to another.
old-location: storage\storportmovememory.htm
old-project: storage
ms.assetid: 5481ae5e-c28a-478e-96be-c6ec8d7f163e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortMoveMemory, StorPortMoveMemory routine [Storage Devices], storage.storportmovememory, storport/StorPortMoveMemory, storprt_7af1ec0d-f1c4-4335-9b80-1aaef26afa35.xml
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
req.ddi-compliance: 
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
-	StorPortMoveMemory
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortMoveMemory function
The <b>StorPortMoveMemory</b> routine copies memory from one buffer to another.

## Syntax

````
STORPORT_API VOID StorPortMoveMemory(
  _In_ PVOID WriteBuffer,
  _In_ PVOID ReadBuffer,
  _In_ ULONG Length
);
````

## Parameters

`WriteBuffer`

Pointer to the destination buffer.

`ReadBuffer`

Pointer to the source buffer.

`Length`

Specifies how many bytes to transfer from <i>ReadBuffer</i> to <i>WriteBuffer</i>.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportmovememory.md">ScsiPortMoveMemory</a>