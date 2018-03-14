---
UID: NF:storport.StorPortReadRegisterUchar
title: StorPortReadRegisterUchar macro
author: windows-driver-content
description: The StorPortReadRegisterUchar routine reads a value from a specified register address.
old-location: storage\storportreadregisteruchar.htm
old-project: storage
ms.assetid: 1edf800d-f097-4d3f-ae89-1b11e4f82f2d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: StorPortReadRegisterUchar, StorPortReadRegisterUchar routine [Storage Devices], storage.storportreadregisteruchar, storport/StorPortReadRegisterUchar, storprt_9f2898e2-6b5e-45ae-9162-57c58a3471f7.xml
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
-	StorPortReadRegisterUchar
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortReadRegisterUchar function
The <b>StorPortReadRegisterUchar</b> routine reads a value from a specified register address.

## Syntax

````
STORPORT_API UCHAR StorPortReadRegisterUchar(
  _In_ PVOID  HwDeviceExtension,
  _In_ PUCHAR Register
);
````

## Parameters

`h`

TBD

`r`

TBD


## Return Value

None

## Remarks

For more information, see <a href="..\storport\nf-storport-scsiportreadregisteruchar.md">ScsiPortReadRegisterUchar</a>. For a buffered version of this routine, see <a href="..\storport\nf-storport-storportreadregisterbufferuchar.md">StorPortReadRegisterBufferUchar</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-storportreadregisterbufferuchar.md">StorPortReadRegisterBufferUchar</a>



<a href="..\storport\nf-storport-scsiportreadregisteruchar.md">ScsiPortReadRegisterUchar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortReadRegisterUchar routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>