---
UID: NF:storport.StorPortReadPortUlong
title: StorPortReadPortUlong macro
author: windows-driver-content
description: The StorPortReadPortUlong routine reads a value from a specified port address.
old-location: storage\storportreadportulong.htm
old-project: storage
ms.assetid: b04ef64a-cf1f-4de5-acb3-e57687f64719
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storport/StorPortReadPortUlong, StorPortReadPortUlong, storprt_3ef5c577-3d75-4797-b5ce-8f36e4080c47.xml, storage.storportreadportulong, StorPortReadPortUlong routine [Storage Devices]
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Storport.lib
-	Storport.dll
apiname:
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

`HwDeviceExtension`



`Port`




## Return Value

None

## Remarks

For more information, see the <a href="..\srb\nf-srb-scsiportreadportulong.md">ScsiPortReadPortUlong</a> routine. For a buffered version of this routine see <a href="..\storport\nf-storport-storportreadportbufferulong.md">StorPortReadPortBufferUlong</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-storportreadportulong.md">StorPortReadPortUlong</a>



<a href="..\srb\nf-srb-scsiportreadportbufferulong.md">ScsiPortReadPortBufferUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadPortUlong routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>