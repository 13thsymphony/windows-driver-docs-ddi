---
UID: NF:storport.StorPortWritePortBufferUlong
title: StorPortWritePortBufferUlong macro
author: windows-driver-content
description: The StorPortWritePortBufferUlong routine writes a value to a specified register address.
old-location: storage\storportwriteportbufferulong.htm
old-project: storage
ms.assetid: 24735e9a-d259-48d1-8efe-8ff1642b6a35
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: StorPortWritePortBufferUlong, StorPortWritePortBufferUlong routine [Storage Devices], storage.storportwriteportbufferulong, storport/StorPortWritePortBufferUlong, storprt_7ab33563-108d-4d20-8205-c3f5ac790f59.xml
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
-	StorPortWritePortBufferUlong
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortWritePortBufferUlong function
The <b>StorPortWritePortBufferUlong</b> routine writes a value to a specified register address.

## Syntax

````
STORPORT_API VOID StorPortWritePortBufferUlong(
  _In_ PVOID  HwDeviceExtension,
  _In_ PULONG Port,
  _In_ PULONG Buffer,
  _In_ ULONG  Count
);
````

## Parameters

`h`

TBD

`p`

TBD

`b`

TBD

`c`

TBD


## Return Value

None

## Remarks

For more information, see <a href="..\storport\nf-storport-scsiportwriteportbufferulong.md">ScsiPortWritePortBufferUlong</a>. For a nonbuffered equivalent of this routine, see <a href="..\storport\nf-storport-storportwriteportulong.md">StorPortWritePortUlong</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-scsiportwriteportbufferulong.md">ScsiPortWritePortBufferUlong</a>



<a href="..\storport\nf-storport-storportwriteportulong.md">StorPortWritePortUlong</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortBufferUlong routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>