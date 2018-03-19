---
UID: NF:storport.StorPortReadPortUlong
title: StorPortReadPortUlong macro
author: windows-driver-content
description: The StorPortReadPortUlong routine reads a value from a specified port address.
old-location: storage\storportreadportulong.htm
old-project: storage
ms.assetid: b04ef64a-cf1f-4de5-acb3-e57687f64719
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReadPortUlong, StorPortReadPortUlong routine [Storage Devices], storage.storportreadportulong, storport/StorPortReadPortUlong, storprt_3ef5c577-3d75-4797-b5ce-8f36e4080c47.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
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
-	StorPortReadPortUlong
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortReadPortUlong function
The <b>StorPortReadPortUlong</b> routine reads a value from a specified port address.

## Syntax

````
STORPORT_API ULONG StorPortReadPortUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Port
);
````

## Parameters

`h`

TBD

`p`

TBD


## Return Value

None

## Remarks

For more information, see the <a href="..\storport\nf-storport-scsiportreadportulong.md">ScsiPortReadPortUlong</a> routine. For a buffered version of this routine see <a href="..\storport\nf-storport-storportreadportbufferulong.md">StorPortReadPortBufferUlong</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-scsiportreadportbufferulong.md">ScsiPortReadPortBufferUlong</a>



<a href="..\storport\nf-storport-storportreadportulong.md">StorPortReadPortUlong</a>