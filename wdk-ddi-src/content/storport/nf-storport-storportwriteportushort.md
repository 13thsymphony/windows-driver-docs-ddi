---
UID: NF:storport.StorPortWritePortUshort
title: StorPortWritePortUshort macro
author: windows-driver-content
description: The StorPortWritePortUshort routine writes a value to a specified register address.
old-location: storage\storportwriteportushort.htm
old-project: storage
ms.assetid: 7655b6a1-2ed4-4e57-b8b5-e7b8ff2dd1e5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortWritePortUshort, StorPortWritePortUshort routine [Storage Devices], storage.storportwriteportushort, storport/StorPortWritePortUshort, storprt_7e675f67-f027-48e7-a41b-b672b0f81d20.xml
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
-	StorPortWritePortUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortWritePortUshort function
The <b>StorPortWritePortUshort</b> routine writes a value to a specified register address.

## Syntax

````
STORPORT_API VOID StorPortWritePortUshort(
  _In_ PVOID   HwDeviceExtension,
  _In_ PUSHORT Port,
  _In_ USHORT  Value
);
````

## Parameters

`h`

TBD

`p`

TBD

`v`

TBD


## Return Value

None

## Remarks

For more information, see <a href="..\srb\nf-srb-scsiportwriteportushort.md">ScsiPortWritePortUshort</a>. For a buffered equivalent of this routine, see <a href="..\storport\nf-storport-storportwriteportbufferushort.md">StorPortWritePortBufferUshort</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportwriteportushort.md">ScsiPortWritePortUshort</a>



<a href="..\storport\nf-storport-storportwriteportbufferushort.md">StorPortWritePortBufferUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWritePortUshort routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>