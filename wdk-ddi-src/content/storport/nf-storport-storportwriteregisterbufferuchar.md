---
UID: NF:storport.StorPortWriteRegisterBufferUchar
title: StorPortWriteRegisterBufferUchar macro
author: windows-driver-content
description: The StorPortWriteRegisterBufferUchar routine transfers a given number of unsigned bytes from a buffer to the HBA.
old-location: storage\storportwriteregisterbufferuchar.htm
old-project: storage
ms.assetid: af8126cd-e931-4106-b543-9c84ee110901
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: storprt_21fa4636-6492-4cb1-9281-6f116f1a7591.xml, StorPortWriteRegisterBufferUchar, StorPortWriteRegisterBufferUchar routine [Storage Devices], storage.storportwriteregisterbufferuchar, storport/StorPortWriteRegisterBufferUchar
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
-	StorPortWriteRegisterBufferUchar
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# StorPortWriteRegisterBufferUchar function
The <b>StorPortWriteRegisterBufferUchar</b> routine transfers a given number of unsigned bytes from a buffer to the HBA.

## Syntax

````
VOID StorPortWriteRegisterBufferUchar(
   IN PVOID  HwDeviceExtension,
   IN PUCHAR Register,
   IN ULONG  Count
);
````

## Parameters

`HwDeviceExtension`



`Register`



`Buffer`



`Count`




## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Header** | storport.h (include Storport.h) |
| **Library** | Storport.lib |

## See Also

<a href="..\storport\nf-storport-scsiportwriteregisterbufferuchar.md">ScsiPortWriteRegisterBufferUchar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20StorPortWriteRegisterBufferUchar routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>