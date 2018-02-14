---
UID: NF:storport.StorPortWritePortBufferUshort
title: StorPortWritePortBufferUshort macro
author: windows-driver-content
description: The StorPortWritePortBufferUshort routine writes a value to a specified register address.
old-location: storage\storportwriteportbufferushort.htm
old-project: storage
ms.assetid: e7b7718b-0c03-4114-8402-9657c49230ad
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: storprt_831acb6e-3529-4e20-897d-e2765b6f7f53.xml, StorPortWritePortBufferUshort, StorPortWritePortBufferUshort routine [Storage Devices], storage.storportwriteportbufferushort, storport/StorPortWritePortBufferUshort
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
-	StorPortWritePortBufferUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortWritePortBufferUshort function
The <b>StorPortWritePortBufferUshort</b> routine writes a value to a specified register address.

## Syntax

````
STORPORT_API VOID StorPortWritePortBufferUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Port,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````

## Parameters

`HwDeviceExtension`



`Port`



`Buffer`



`Count`




## Return Value

None

## Remarks

For more information, see <a href="..\srb\nf-srb-scsiportwriteportbufferushort.md">ScsiPortWritePortBufferUshort</a>. For a non-buffered equivalent of this routine, see <a href="..\storport\nf-storport-storportwriteportushort.md">StorPortWritePortUshort</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportwriteportbufferushort.md">ScsiPortWritePortBufferUshort</a>



<a href="..\storport\nf-storport-storportwriteportushort.md">StorPortWritePortUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortBufferUshort routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>